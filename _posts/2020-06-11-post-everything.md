---
layout: post
title: Um Post de Exemplo
feature-img: "assets/img/pexels/lion.jpg"
thumbnail: "assets/img/thumbnails/desk-messy.jpeg"
tags: [Estatística, Análise]
comments: true
author: leonaralves
excerpt_separator: <!--more-->
---

Um bom resumo para o início do blog seria algo de 1 parágrafo com aproximadamente três linhas. Hopefully you will find enough information about how to set images in your blog here. 😉 ⚠️
This is an example of a post which includes a feature image specified in the front matter of the post. 
<!--more-->

# Análise Estatística 
<!-- To be placed at the beginning of the post, it is where the table of content will be generated -->
* TOC
{:toc}

The feature image spans the full-width of the page, and is shown with the title on permalink pages:   😉 ⚠️

```yaml
dados = read.csv('dados.csv')
head(dados)
```

You can also use a thumbnail, a smaller version of the same image to improve loading of the page.
The thumbnail will also be used when you share your article on other platform (linkedin, whatsapp, facebook, ...).

>  - Citando alguma frase importante

> Destacando **uma** frase **importante**

## Adicionando imagens

Vamos colocar duas imagens uma ao lado da outra. Elas devem ser todas do mesmo tamanho e ficarão bem alinhadas.

{% highlight ruby %}
{% raw %}
{% include aligner.html images="pexels/book-glass.jpeg,triangle.png" %}
{% endraw %}
{% endhighlight %}

{% include aligner.html images="pexels/book-glass.jpeg,pexels/desk-messy.jpeg" %}

### Adicionando três imagens

Colocando três imagens uma ao lado da outra. Here you have two images side by side, but you can set more and set the amount per columns 
(by specifying the number of columns or let it be automatic using `"auto"`):

{% highlight ruby %}
{% raw %}
{% include aligner.html images="pexels/cabin.png,pexels/cake.png,pexels/circus.png" column=3 %}
{% endraw %}
{% endhighlight %}

{% include aligner.html images="pexels/cabin.png,pexels/cake.png,pexels/circus.png" column=3 %}

it also works with only one images, it is made to display it smaller than normally. Colocando um link aqui [xukimseven/HardCandy-Jekyll](https://github.com/xukimseven/HardCandy-Jekyll) ou assim [xukimseven](https://github.com/xukimseven)
However you can just use the Markdown way of doing it to get the image normal sized and centered.

{% highlight ruby %}
{% raw %}
# Adicionando um comentário
![Travel]({{ "/assets/img/pexels/story.jpeg" | relative_url}})
# Adicionando um segundo comentário
{% include aligner.html images="pexels/story.jpeg" %}
{% endraw %}
{% endhighlight %}

{% include aligner.html images="pexels/story.jpeg" %}

## Adicionando Tabelas

Vamos adicionar uma tabela,  veja como é simples:

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

## Imagem adicionada pelo Markdown

![Image of a glass on a book]({{ "/assets/img/pexels/book-glass.jpeg" | relative_url }})

## Adicionando fórmulas

Highlighting for code in Jekyll is done using Base16 or Rouge. This theme makes use of Rouge by default.

{% highlight js %}
// count to ten
for (var i = 1; i <= 10; i++) {
    console.log(i);
}

// count to twenty
var j = 0;
while (j < 20) {
    j++;
    console.log(j);
}
{% endhighlight %}

Type on Strap uses KaTeX to display maths. Equations such as $$S_n = a \times \frac{1-r^n}{1-r}$$ can be displayed inline.

Alternatively, they can be shown on a new line:

$$ f(x) = \int \frac{2x^2+4x+6}{x-2} $$

Vamos adicionar mais fórmulas aqui

$$ f(x) = \int \int \frac{3x^2+4x+6}{x-2} $$

## Colocando uns códigos

Maneiras de colocar os códigos.

### GFM Code Blocks

GitHub Flavored Markdown [fenced code blocks](https://help.github.com/articles/creating-and-highlighting-code-blocks/) are supported. To modify styling and highlight colors edit `/_sass/syntax.scss`.

```css
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
```

{% highlight scss linenos %}
.highlight {
  margin: 0;
  padding: 1em;
  font-family: $monospace;
  font-size: $type-size-7;
  line-height: 1.8;
}
{% endhighlight %}

```html
{% raw %}<nav class="pagination" role="navigation">
  {% if page.previous %}
    <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
  {% endif %}
  {% if page.next %}
    <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
  {% endif %}
</nav><!-- /.pagination -->{% endraw %}
```

```ruby
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
```

### Code Blocks in Lists

Indentation matters. Be sure the indent of the code block aligns with the first non-space character after the list item marker (e.g., `1.`). Usually this will mean indenting 3 spaces instead of 4.

1. Do step 1.
2. Now do this:

   ```ruby
   def print_hi(name)
     puts "Hi, #{name}"
   end
   print_hi('Tom')
   #=> prints 'Hi, Tom' to STDOUT.
   ```
    
    ```python
   def print_hi(name)
     print('Your name is', name)
   print_hi('Tom')
   #=> prints 'Hi, Tom' to STDOUT.
   ```

    ```R
   # Esse é um código em R
   funcao = function(dados):
      print('Oi, eu me chamo Leonara')
   ```

3. Now you can do this.

# Finalização

Aqui é a `conclusão` do seu post.

* Seja coerente
* Explique bem os detalhes do seu post
* Seja criativo

[^1]: 
    {% include citation.html key="ref1" %}