#{ViaJS}
Via é uma pequena, porém poderosa biblioteca javascript que facilita o carregamento de conteúdo de uma página para outra dinâmicamente. Sem refresh.
###Demonstração

[Veja uma Demonstração da ViaJS](http://viajs.herokuapp.com/)

###Baixando

Clone o repositório usando
```
git clone https://github.com/matheusviegas/ViaJS.git
```

ou clique no botão __Download ZIP__


###Como Usar 

#####Passo 1: Importe o script __app.js__ 

```html
<script src='lib/app.js'></script>
```

#####Passo 2: Especifique __onde__ o conteúdo será carregado
```html
<div class="conteudo" via-views></div>
```
O atributo __via-views__ deve estar na div que receberá o conteúdo. É assim que o script identifica onde o conteúdo deve ser carregado.

Especifique todas as _views_ que poderão ser carregadas na div e especifique uma _view_ padrão (defaultView). Essa _view_ padrão será carregada caso o usuário tente acessar alguma página que não está listada nas _views_ como acessível.

#####Passo 3: Instancie um objeto da classe __Via__, chame o método __init__ e passe como parâmetro o array de _views_.

Exemplo:

```javascript
var views = {
    home:{
        templateUrl:'views/index.html'  
    },
    about: {
        templateUrl: 'views/about.html'
    },
    contact:{
        templateUrl:'views/contact.html'
    },
    defaultView: {
        view: 'home'
    }
}

var via = new Via(); // Instancia um objeto da classe Via()

via.init(views); // Inicia as views
```

#####Passo 4: Use uma tag < a > com o atributo via-link

```html
<ul class="nav navbar-nav">
    <li class=""><a via-link href="home">Home</a></li>
    <li><a via-link href="about">About</a></li>
    <li><a via-link href="contact">Contact</a></li>
</ul>
```

Lembre-se de colocar no atributo __href__ o mesmo nome da _view_ que você informou no _array de views_ e adicione o atributo __via-link__ para todas as tags __a__ que você usará para carregar o conteúdo.
