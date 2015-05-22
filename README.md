# Guia de Estudos PHP

## O que é?

Originalmente, o Guia de Estudos PHP era um projeto pequeno com um guia passo-a-passo
com informações necessárias para passar na [certificação PHP5.3 ZCE][1].

Agora, o foco é ir um pouco além da certificação Zend e ser um bom lugar para
começar sua experiência com PHP5.3 ou, se você já é um desenvolvedor web experiente,
para retomar os fundamentos e lembrar alguns detalhes.

>Para tópicos avançados e boas práticas, por favor, considere dar uma olhada
>no projeto [PHP The Right Way][2], mantido por [Josh Lockhart][3] com apoio da comunidade.

## Onde?

Neste momento, o projeto original está disponível em [http://php-guide.evercodelab.com/][4] e
hospedado no [GitHub.Pages](http://pages.github.com).

A tradução em português do Brasil (pt_BR) está disponível no endereço [https://phpsp.github.io/php-guide-pt_BR][13].

## Fontes

Todo conteúdo foi obtido de diferentes fontes e tutoriais.

* Zend PHP 5.0 Certification Course por Paul Reinheimer
* Zend PHP 5 Certification Study Guide
* Zend PHP 5.3 Study Guide v1
* [Blog Read The Web][5]
* <http://www.php.net/manual/en/>
* <http://zend-php.appspot.com/>

O guia original foi estruturado no Google Docs e depois publicado como [pdf][6].

## Quem?

O projeto foi feito principalmente por [Roma Lapin][7] com apoio da [Evercode Lab][8].

## Traduções
O Guia de Estudos PHP está sendo traduzido para as seguintes linguagens:

[Português Brasileiro][12]

## Como Contribuir

De início todo conteúdo foi montado para ser utilizado para a certificação ZCE do PHP5.3. Então
ele tinha como foco ser curto e limitado. Por agora sinta-se livre para contribuir.
Todas sugestões de conteúdo e design são bem vindas.

Para contribuir, por favor, faça o seguinte.

* [Crie um fork deste projeto][9]
* Realize um clone do seu fork
* Crie um branch que conterá sua alteração: `git checkout -b minha_alteracao`
* Adicione o que deseja
* Faça o push para seu repositório `git push origin minha_alteracao`
* [Envie um Pull Request][10]

>Nota importante: este projeto é um fork do projeto original, com foco em sua tradução.
> Se você deseja de fato enviar uma nova seção prefira utilizar o [repositório oficial][12]
>e, mais tarde, este repositório será sincronizado e seremos capazes de traduzir sua contribuição.

## Layout do projeto e detalhes

Todo este projeto segue um [layout de projeto jekyll][11] padrão.

Cada seção da certificação está presente na pasta `pages`. Toda sub-seção é
parte de uma página.

É utilizado o Pygments para realizar o highlighting do código.

Cada página deve conter as seguintes variáveis em `YAML Front Matter`:

* title – Título da página
* layout - geralmente é "page"

Os menus estão dispostos em `_includes/menu`.

[1]: http://www.zend.com/en/services/certification/php-5-certification/ "PHP5.3 ZCE certification"
[2]: http://www.phptherightway.com/ "PHP The Right Way"
[3]: https://github.com/codeguy
[4]: http://php-guide.evercodelab.com/ "http://php-guide.evercodelab.com/"
[5]: http://readtheweb.info/index.php?s=Zend+PHP+5+Certification+Exam&submit=Go
[6]: http://victimofbabylon.com/zce-php-53-study-guide
[7]: https://github.com/memphys
[8]: http://www.evercodelab.com/
[9]: http://help.github.com/fork-a-repo/
[10]: http://help.github.com/send-pull-requests/
[11]: http://jekyllrb.com/docs/usage/
[12]: https://github.com/EvercodeLab/php-guide
[13]: https://phpsp.github.io/php-guide-pt_BR
