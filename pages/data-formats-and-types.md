---
layout: page
title: "Formatos e tipos de dados"
description: ""
---
{% include JB/setup %}

{% include menu/data-formats-and-types.md %}


* * *

## XML

Bem estruturado

* Apenas uma tag de nível raiz
* Tags são abertas e fechadas corretamente
* Entidades devem ser bem estruturadas

Válido

* Bem estruturado
* Contém um DTD (Definição de Tipo de Documento)
* Segue o DTD que contém


* * *

## Interpretando XML


DOM

* Document Object Model
* Carrega todo o documento na memória RAM, e em seguida cria uma representação em forma de árvore
* <http://php.net/manual/pt_BR/book.dom.php>

SimpleXML

* Todos os objetos são instâncias da classe SimpleXMLElement
* Utiliza método DOM
* Muito fácil de ser utilizado
* Faz grande uso de memória
* <http://php.net/manual/pt_BR/book.simplexml.php>


* * *

## SimpleXml


* `$xml = simplexml_load_string($library);`
* `object simplexml_load_file ( string $filename [, string $class_name [, int $options [, string $ns [, bool $is_prefix]]]] )`
* `SimpleXMLElement::xpath()`
* Adicionando elementos
   * `SimpleXMLElement::addChild()`
   * `SimpleXMLElement::addAttribute()`
* `asXML()`
* `$library->book[0] = NULL;` - para remover elementos filho
* `children()` - retorna o iterador para subnós
* `attributes()`
* Namespaces
   * `SimpleXMLElement::getDocNamespaces()`
   * `SimpleXMLElement::getNamespaces()`


* * *

## DOM

{% highlight php5 linenos %}
<?php
$dom = new DomDocument();
$dom->load("library.xml");
$dom->loadXML($xml);

DomDocument::loadHtmlFile(); // e DomDocument::loadHTML()
DomDocument::save(); // (para um arquivo)
DomDocument::saveXML(); // (para uma string)
DomDocument::saveHTML(); // (também para uma string, mas salva um documento HTML ao invés de um arquivo XML)
DomDocument:saveHTMLFile(); // (para um arquivo em formato HTML).
{% endhighlight %}

DomNode

* `DomDocument::createElement()`
* `DomDocument::createElementNS()`
* `DomDocument::createTextNode()`
* `DomNode::appendChild()`
* `DomNode::insertBefore()`
* `DomNode::cloneNode()`
* `DomNode::setAttributeNS()`

Removendo

* `DomNode::removeAttribute()`
* `DomNode::removeChild()`
* `DomCharacterData::deleteData()`

Importando 
* 
* `dom_import_simplexml($sxml)`
* `simplexml_import_dom($dom);`


* * *

## XPath


* Padrão da W3C suportado por diversas linguagens
* Combina o mojo do Regex com alguns resultados como SQL
* `$xpath = new DomXPath($dom);`
* Uma chamada para `DomXpath::query()` irá retornar um objeto `DomNodeList`;
* <http://www.w3schools.com/xpath/xpath_syntax.asp>


* * *

## Buscas XPath


* `xpath("item")` - irá retornar um array de objetos "item"
* `xpath("/bookshelf")` - irá retornar todos os filhos do nó `</bookshelf>`
* `xpath("//book")` - irá retornar um array de valores dos nós com titulo "book"
* `xpath(".")` - irá retornar o nó atual `<bookshelf>`
* `xpath("..")` - irá retornar um array vazio, pois o nó raiz `<bookshelf>` não possui um elemento pai.


* * *

## Web Services


* Cobertura genérica que descreve como sistemas diferentes podem se integrar uns com os outros na web
* Muitos dos maiores sites oferecem alguma forma de web service:
   * Amazon
   * FedEx
   * eBay
   * PayPal
   * del.icio.us
* Alguém possui dados dos quais você precisa
* Mais fácil do que realizar page scraping (e também mais confiável)
* Automatiza processos
* Fornece informações adicionais para seus clientes


* * *

## REST


* Representational State Transfer
* Requests aparentam como os de formulários completamente preenchidos, pode utilizar tanto GET como POST
* Response é um documento XML/JSON
* O Request e Response são definidos pelo fornecedor do serviço
* Serviços que utilizam da arquitetura REST são chamados de serviços RESTful; aqueles que utilizam ou fornecem serviços RESTful, as vezes são referenciados como RESTafarians, como forma de humor.
* <http://library.example.com/api.php?devkey=123&action=search&type=book&keyword=style>



* * *

## SOAP


* Simple Object Access Protocol (Não significa mais nada além disso)
* Requests são enviados utilizando POST
* Requests são encapsulados com um SOAP Envelope
* Responses são documentos XML com Envelope e seções Body similares
* WSDL Documents
   * SOAP web services são descritos pelos arquivos WSDL
   * São designados para consumo automatizado (não humano)
   * Descrevem os métodos oferecidos pelo web service, os parâmetros requeridos, e o tipo de retorno, assim como todos os tipos complexos requisitados pelo serviço
* PHP5 possui suporte nátivo ao SOAP

As funções (geralmente) pegam o arquivo WSDL como entrada, e criam um objeto que imita os serviços do webservice:

{% highlight php5 linenos %}
<?php
$client = new SoapClient("http://soap.amazon.com/schemas2/AmazonWebServices.wsdl");
{% endhighlight %}

Chamada à API:

{% highlight php5 linenos %}
<?php
$result = $client->KeywordSearchRequest($params);
{% endhighlight %}

Debugging

{% highlight php5 linenos %}
<?php
$client = new SoapClient('http://api.google.com/GoogleSearch.wsdl', array('trace' => 1));
$client->__getLastRequestHeaders();
$client->__getLastRequest();
{% endhighlight %}

[PHP5 SOAP Server](http://php.net/manual/pt_BR/class.soapserver.php)

* Não inclui a criação de arquivos WSDL (NuSOAP e Zend Studio incluem)
* Você ainda pode fornecer um serviço seja pelo uso de um arquivo WSDL externo, ou meramente definindo métodos de acesso

{% highlight php5 linenos %}
<?php
$options = array('uri' => 'http://example.org/soap/server/');
$server = new SoapServer(NULL, $options);
$server->setClass('MySoapServer');
$server->handle();
{% endhighlight %}


* * *

## Data e Hora

<http://php.net/manual/en/class.datetime.php>
<br/>
<http://php.net/manual/pt_BR/book.datetime.php>


* * *

## JSON e AJAX

<http://php.net/manual/pt_BR/book.json.php>
