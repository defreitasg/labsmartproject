# labsmartproject
Criação de site navegavel

Utilizando do programa Brackets no qual me sinto mais a vontade para fazer o primeiro processo de estrutura do site e organização de docs e pastas e também uma orientação de quantos arquivos seriam necessários.

Iniciei a estruturação do site criando o corpo index.html como minha página home.
Procurei formatar um site responsivo, o qual pudesse ser acessado em diversas plataformas (tablet, celular, computadores/notebooks em geral..). Para isso, criei 3 documentos distintos utilizando .CSS: small.css, para ser visualizado em menor resolução (Ex: celulares); medium.css, para resoluções de médio porte (Ex: tablets); e large.css, em resoluções maiores (Ex: notebooks).
PS: estes 3 estruturas poderiam ser feitas em somente um doc .CSS, porém por preferencia e organização própria criei em 3 docs separados.
<!-----APENAS ESTRUTURA DO DOC SMALL.CSS PARA EXEMPLO----->

	.size-div {
		position: relative;
		width: 500px;
		margin: 0 auto;
		height: 500px;
		background-color: #000000
	}

Primeiramente procurei adicionar um MENU que se tornar-se dinâmico e agressivo que fluisse ao meu site responsivo. 

<!------CODIGO HTML MENU--------> index.html

	<header>
			<input type="checkbox" id="btn-menu">
			<label for="btn-menu">&#9776;</label>
			<nav class="menu">
				<ul>
					<li><a href="index.html">Home</a></li>
					<li><a href="sobre.html">Sobre</a></li>
					<li><a href="portfolio.html">Portfolio</a></li>
					<li><a href="contato.html">Contato</a></li>
					<li><a href="http://www.lipsum.com/">Site</a></li>
				</ul>
			</nav>
					
	</header>
		
OBS: onde &#9776; é o botão em codigo html de alteração do menu horizontal para uma barra vertical ao clicar no checkbox, assim ocupando menos px de uma tela small size.

Após finalizar o cabeçalho do meu site, decidi procurar um conteúdo para o mesmo, como já havia decidido utilizar o Lorem Ipsum para ocupar linhas de txt do site, aproveitei para fazer a produção também em cima desta ideia.

Após o corpo HTML do meu cabeçalho estar pronto, parti para a codificação utilizando CSS para dar vida e estruturação ao meu menu.

<!------AQUI FORMATEI MEU MENU DE FORMA SE TORNASSE RESPONSIVO EM DIVERSAS PLATAFORMAS--------> style.css
	
	@media(max-width: 768px){
	
		header label{
			display: block;
		}
			.menu ul{
				position: absolute;
				background-color: #2f2f2f;
				width: 70%;
				flex-direction: column;
				margin-left: -70%;
			}

			.menu li a{
				border-top:1px solid #efefef;
			}

			#btn-menu:checked ~ .menu ul{
				margin-left:0;
			}
		}


<!----------CODIGO CSS PARA O MENU TRABALHAR EM CHECKBOX EM BAIXA TAXA DE PX E TIME DE ANIMAÇÃO----> style.css

	.menu ul{
		list-style: none;
		margin: 0;
		padding: 0;
		display: flex;
		transition: all 1s;
	}

Ao finalizar o MENU parti para a estrutura do corpo HOME do meu site, adicionando uma logo de entrada em .GIF para trazer movimento e deixar de certa forma orgânico o visual, abaixo um breve texto e outra logo de forma mais formal porém procurando buscar algo mais agressivo que combinasse com o menu.

Abaixo do texto criei um codigo que interagisse como uma clickbox VER MAIS>>> ou <a> que levasse o visitante a outra página do site destinada ao conteúdo SOBRE.

<!-----CÓDIGO CLICKBOX VER MAIS>>>------> index.html

	<div>
		<p>
		<a href="sobre.html" id="bntInfo" class="#">Leia Mais >></a>
		</p>
	</div>
	

Na página SOBRE apenas foram adicionados textos utilizando cod <div> <p> <h1> e style="margin" para dar formatação da margem dos textos adicionados.


<!----------COD BODY DE TODO SITE EM CSS-----> style.css
	body {
		background-color:#000;
		padding:0;
		margin:0;
	
	
	}

<!--------COD DE CONTEUDO DO SITE EM CSS-----> style.css
	.conteudo{
		background:#FFF;
		box-shadow:1px 1px 10px rgba(0,0,0,0.5);
		-webkit-box-shadow:1px 1px 10px rgba(0,0,0,0.5);
		-moz-box-shadow:1px 1px 10px rgba(0,0,0,0.5);
	}

	.conteudo p{
		font-size:20px;
		padding:30px;
	}

<!----COD PARA TITULOS DE CONTEUDO DO SITE EM CSS------->
	h2{
		color:#a3e0ff;
		font-size:28px;
		margin-bottom:50px;
		text-shadow:1px 1px 7px rgba(0,0,0,0.5);
		-webkit-box-shadow:1px 1px 7px rgba(0,0,0,0.5);
		-moz-box-shadow:1px 1px 7px rgba(0,0,0,0.5);
	}
	
Na pagina PORTIFOLIO utilizei o javascript para criar o meu slideshow scriptado.

<!--------COD DE SCRIPTUTILIZADO-------> portfolio.html
	<script type="text/javascript" src="javascripts/jquery.min.js"> </script>
		<script type="text/javascript" src="javascripts/jquery.cycle.all.js"> </script>

		<script type="text/javascript">
			$(document).ready(function() {
				$('.slides ul').cycle({
					fx:'fade',
					speed: 2000,
					timeout: 3000,
				});
			});

		</script>

<!--------------COD DAS IMG SCRIPTADAS EM HTML UTILIZANDO A CLASS="SLIDES"-----> portfolio.html
	<div class="slides">
			<ul>
				<li> <img src="img/imagem1.jpg" alt="Slide 1" width="1347" height="400" /> </li>
				<li> <img src="img/lorem1.jpg" alt="Slide 2" width="1347" height="400" /> </li>
				<li> <img src="img/lorem2.png" alt="Slide 3" width="1347" height="400" /> </li>
				<li> <img src="img/lorem3.jpg" alt="Slide 4" width="1347" height="400" /> </li>
			</ul>
	</div>
	
