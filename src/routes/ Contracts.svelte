<script>

    export let titles = [
      { id: 'J---aiyznGQ', name: 'Договор купли продажи', desc: 'Текст договора', isActive: 'false'},
      { id: 'z_AbfPXTKms', name: 'Договор на оказание услуг', desc: 'Текст договора 2',  isActive: 'false'},
      { id: 'OUtn3pvWmpg', name: 'Договор №652344', desc: 'Текст договора 3', isActive: 'false' }
  ];


 
 
</script>


<div class="row">
    <div class="col col-md">
        <main>
            <input type="checkbox" id="nav-toggle" hidden>
        
            <nav class="nav">
         
                <label for="nav-toggle" class="nav-toggle" onclick></label>
        
                <h2 class="logo"> 
                    <a href="/">Pharm</a> 
                </h2>
        
                <div class="nav-items">
                    <ul >
                        <li class="active"><a href="#/cotractpage/">Договора</a>
                        <li><a href="#2">Кантрагенты</a>
                        <li><a href="#3">Еще что-то</a>
            
                    </ul>
                </div>
                
            </nav>
        </main>
    </div>

    <div class="col col-md ">
        
            
        
        
        <div class="wrapper">

            <div class="contracts">
                        
                {#each titles as title, i }

                    <ul>
                        <li><a href="#" class:active={title.isActive === 'true' ? 'active' : '' }  
                            on:click|preventDefault="{() => title.isActive = 'true'}">
                            {title.name}</a>
                        </li>
                    </ul>
                        
                        
                {/each}
            </div>
            
                       
                
        
        
        </div>
        
        
        <div class="wrapper">
            <div class="card card-2">
                <div class="container container-2">
                    <h2><a href="#">a1</a></h2>
                    <p>a2</p>
                </div>
            </div>
        </div>
    </div>
    
</div>


<style>

.contracts .active {
		background-color: #ff3e00;
		color: white;
	}

    .row {
        height: 1000px;
    }

.wrapper {
    margin-left: 800px;
}

.container a {
    text-decoration: none;
    
}

.container p {
    font-size: 18px;
}

.contracts {
	margin-top: 20px;
	width: 600px;
	border:1px solid darkblue;
	height: 200px;
    padding-left: 15px;
	
}

.contracts li{
	list-style: none;
	
}

.contracts li a{
    color: #333;
    text-decoration: none;
	
}

.contracts h3 {
    margin: 0;

}


.card {
    margin-top: 20px;
	width: 600px;
	border:1px solid darkblue;
	height: 200px;
    padding-left: 15px;
}

main {
    margin-top: 150px;
    display: flex;
    flex-direction: column;
}



/* Styles for navigation*/

    .nav {
        width: 320px;
        min-width: 320px;
        height: 100vh;
        position: fixed;
        top: -15px;
        bottom: 0;
        margin: 0;
        left: -320px;
        padding: 15px 20px;
        -webkit-transition: left 0.3s;
        -moz-transition: left 0.3s;
        transition: left 0.3s;
        background: #d30a12;
        z-index: 2000;
    }

    .nav-items {
        margin-top: 80px;
    }
    
    
    
    
    
    .nav-toggle {
        position: absolute;
        left: 320px;
        top: 1em;
        padding: 0.5em;
        background: inherit;
        color: #dadada;
        cursor: pointer;
        /* размер шрифта */
        font-size: 1.2em;
        line-height: 1;
        /* всегда поверх других элементов страницы */
        z-index: 2001;
        /* анимируем цвет текста при наведении */
        -webkit-transition: color .25s ease-in-out;
        -moz-transition: color .25s ease-in-out;
        transition: color .25s ease-in-out;
    }
    
    
    /* определяем текст кнопки 
     * символ Unicode (TRIGRAM FOR HEAVEN)
    */
    
    .nav-toggle:after {
        content: '\2630';
        text-decoration: none;
    }
    
    
    /* цвет текста при наведении */
    
    .nav-toggle:hover {
        color: #f4f4f4;
    }
    
    
    /**
     * Скрытый чекбокс (флажок)
     * невидим и недоступен :)
     * имя селектора атрибут флажка
     */
    
    #nav-toggle {
        position: absolute;
        display: none;
    }
    
    
    /**
     * изменение положения переключателя 
     * при просмотре на мобильных устройствах
     * когда навигация раскрыта, распологаем внутри панели
    */
    
    #nav-toggle:checked ~ .nav > .nav-toggle {
        left: auto;
        right: 2px;
        top: 1em;
    }
    
    
    /**
     * Когда флажок установлен, открывается панель
     * используем псевдокласс:checked
     */
    
    #nav-toggle:checked ~ .nav {
        left: 0;
        box-shadow:4px 0px 20px 0px rgba(0,0,0, 0.5);
        -moz-box-shadow:4px 0px 20px 0px rgba(0,0,0, 0.5);
        -webkit-box-shadow:4px 0px 20px 0px rgba(0,0,0, 0.5);
        overflow-y: auto;
    }
    
    
    /* 
     * смещение контента страницы
     * на размер ширины панели,
     * фишка необязательная, на любителя
    */
    
    
    /*
     * изменение символа переключателя,
     * привычный крестик (MULTIPLICATION X), 
     * вы можете испльзовать любой другой значок
    */
    
    #nav-toggle:checked ~ .nav > .nav-toggle:after {
        content: '\2715';
    }
    
    
    /**
     * профиксим баг в Android <= 4.1.2
     * см: http://timpietrusky.com/advanced-checkbox-hack
     */
    
    main {
        -webkit-animation: bugfix infinite 1s;
    }
    
    @-webkit-keyframes bugfix {
        to {
          padding: 0;
        }
    }
    
    
    /**
     * позаботьтимся о средних и маленьких экранах
     * мобильных устройств
     */
    
    @media screen and (min-width: 320px) {
       main {
          margin: 0;
          overflow-x: hidden;
        }
    }
    
    @media screen and (max-width: 320px) {
        main{
          margin: 0;
          overflow-x: hidden;
        }
        .nav {
          width: 100%;
          box-shadow: none
        }
    }

    @media(max-width: 1428px) {
        .wrapper {
            margin-left: 600px;
        }
    }

    @media(max-width: 1225px) {
        .wrapper {
            margin-left: 400px;
        }
    }

    @media(max-width: 1225px) {
        .wrapper {
            margin-left: 400px;
        }
    }

    @media(max-width: 1025px) {
        .contracts {
            width: 250px;
        }

        .wrapper .card {
            width: 250px;
            height: 250px;
        }
    }
    
    
    /**
     * Формируем стиль заголовка (логотип) панели 
    */
    
    .nav h2 {
        width: 90%;
        height: 100px;
        padding: 0;
        margin: 10px 0;
        text-align: center;
        text-shadow: rgba(255, 255, 255, .1) -1px -1px 1px, rgba(0, 0, 0, .5) 1px 1px 1px;
        font-size: 1.3em;
        line-height: 1.3em;
        opacity: 0;
        transform: scale(0.1, 0.1);
        -ms-transform: scale(0.1, 0.1);
        -moz-transform: scale(0.1, 0.1);
        -webkit-transform: scale(0.1, 0.1);
        transform-origin: 0% 0%;
        -ms-transform-origin: 0% 0%;
        -moz-transform-origin: 0% 0%;
        -webkit-transform-origin: 0% 0%;
        transition: opacity 0.8s, transform 0.8s;
        -ms-transition: opacity 0.8s, -ms-transform 0.8s;
        -moz-transition: opacity 0.8s, -moz-transform 0.8s;
        -webkit-transition: opacity 0.8s, -webkit-transform 0.8s;
    }
    
    .nav h2 a {
        color: #dadada;
        text-decoration: none;
        text-transform: uppercase;
    }
    
    
    /*плавное появление заголовка (логотипа) при раскрытии панели */
    
    #nav-toggle:checked ~ .nav h2 {
        opacity: 1;
        transform: scale(1, 1);
        -ms-transform: scale(1, 1);
        -moz-transform: scale(1, 1);
        -webkit-transform: scale(1, 1);
    }
    
    
    /**
     * формируем непосредственно само меню
     * используем неупорядоченный список для пунктов меню
     * прикрутим трансфомации и плавные переходы
     */
    
    .nav > .nav-items ul {
        display: block;
        margin: 0;
        padding: 0;
        list-style: none;
    }
    
    .nav > .nav-items ul > li {
        line-height: 2.5;
        opacity: 0;
        text-decoration: none;
        -webkit-transform: translateX(-50%);
        -moz-transform: translateX(-50%);
        -ms-transform: translateX(-50%);
        transform: translateX(-50%);
        -webkit-transition: opacity .5s .1s, -webkit-transform .5s .1s;
        -moz-transition: opacity .5s .1s, -moz-transform .5s .1s;
        -ms-transition: opacity .5s .1s, -ms-transform .5s .1s;
        transition: opacity .5s .1s, transform .5s .1s;
    }
    
    [id='nav-toggle']:checked ~ .nav .nav-items > ul > li {
        opacity: 1;
        -webkit-transform: translateX(0);
        -moz-transform: translateX(0);
        -ms-transform: translateX(0);
        transform: translateX(0);
    }
    
    
    /* определяем интервалы появления пунктов меню */
    
    .nav > .nav-items > ul > li:nth-child(2) {
        -webkit-transition: opacity .5s .2s, -webkit-transform .5s .2s;
        transition: opacity .5s .2s, transform .5s .2s;
    }
    
    .nav > .nav-items ul > li:nth-child(3) {
        -webkit-transition: opacity .5s .3s, -webkit-transform .5s .3s;
        transition: opacity .5s .3s, transform .5s .3s;
    }
    
    .nav > .nav-items > ul > li:nth-child(4) {
        -webkit-transition: opacity .5s .4s, -webkit-transform .5s .4s;
        transition: opacity .5s .4s, transform .5s .4s;
    }
    
    .nav > .nav-items >  ul > li:nth-child(5) {
        -webkit-transition: opacity .5s .5s, -webkit-transform .5s .5s;
        transition: opacity .5s .5s, transform .5s .5s;
    }
    
    .nav > .nav-items >  ul > li:nth-child(6) {
        -webkit-transition: opacity .5s .6s, -webkit-transform .5s .6s;
        transition: opacity .5s .6s, transform .5s .6s;
    }
    
    .nav > .nav-items >  ul > li:nth-child(7) {
        -webkit-transition: opacity .5s .7s, -webkit-transform .5s .7s;
        transition: opacity .5s .7s, transform .5s .7s;
    }
    
    
    /**
     * оформление ссылок пунктов меню
     */
    
    .nav > .nav-items > ul > li > a {
        display: inline-block;
        position: relative;
        padding: 0;
        font-family: 'Open Sans', sans-serif;
        font-weight: 300;
        font-size: 1.2em;
        color: #dadada;
        width: 100%;
        text-decoration: none;
        /* плавный переход */
        -webkit-transition: color .5s ease, padding .5s ease;
        -moz-transition: color .5s ease, padding .5s ease;
        transition: color .5s ease, padding .5s ease;
    }
    
    
    /**
     * состояние ссылок меню при наведении
     */
    
    .nav > .nav-items > ul > li > a:hover,
    .nav > .nav-items > ul > li > a:focus {
        color: white;
        padding-left: 15px;
    }
    
    
    /**
     * линия подчеркивания ссылок меню
     */
    
    .nav > .nav-items > ul > li > a:before {
        content: '';
        display: block;
        position: absolute;
        right: 0;
        bottom: 0;
        height: 1px;
        width: 100%;
        -webkit-transition: width 0s ease;
        transition: width 0s ease;
    }
    
    .nav > .nav-items > ul > li > a:after {
        content: '';
        display: block;
        position: absolute;
        left: 0;
        bottom: 0;
        height: 1px;
        width: 100%;
        background: #3bc1a0;
        -webkit-transition: width .5s ease;
        transition: width .5s ease;
    }
    
    
    /**
     * анимируем линию подчеркивания 
     * ссылок при наведении
     */
    
    .nav > .nav-items > ul > li > a:hover:before {
        width: 0%;
        background: #3bc1a0;
        -webkit-transition: width .5s ease;
        transition: width .5s ease;
    }
    
    .nav > .nav-items > ul > li > a:hover:after {
        width: 0%;
        background: transparent;
        -webkit-transition: width 0s ease;
        transition: width 0s ease;
    }
    
    
    /* фон затемнения на основной контент 
     * при этом элементы блокируютя
     * спорная такая фича, если оно вам надо
     * просто раскомментируйте
    */
    
    /*
    .mask-content {
        display: block;
        position: fixed;
        top: 0;
        left: 0;
        z-index: 1000;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.4);
        visibility: hidden;
        opacity: 0;
    }
    
    [id='nav-toggle']:checked ~ .mask-content {
        visibility: visible;
        opacity: 1;
        -webkit-transition: opacity .5s, visibility .5s;
        transition: opacity .5s, visibility .5s;
    }
    */
    </style>

