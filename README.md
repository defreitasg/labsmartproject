# labsmartproject
Criação de site navegável

Utilizando do programa Brackets no qual me sinto mais a vontade para fazer o primeiro processo de estrutura do site e organização de docs e pastas e também uma orientação de quantos arquivos seriam necessários.

Iniciei a estruturação do site criando o corpo index.html como minha página home.
Procurei formatar um site responsivo, o qual pudesse ser acessado em diversas plataformas (tablet, celular, computadores/notebooks em geral..). Para isso, criei 3 documentos distintos utilizando .CSS: small.css, para ser visualizado em menor resolução (Ex: celulares); medium.css, para resoluções de médio porte (Ex: tablets); e large.css, em resoluções maiores (Ex: notebooks).
PS: estas 3 estruturas poderiam ser feitas em somente um doc .CSS, porém por preferencia e organização própria criei em 3 docs separados.
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

Abaixo do texto criei um codigo hiperlink que interagisse como uma clickbox VER MAIS>>> ou <a> que levasse o visitante a outra página do site destinada ao conteúdo SOBRE.

<!-----CÓDIGO HIPERLINK VER MAIS>>>------> index.html

	<div>
		<p>
		<a href="sobre.html" id="bntInfo" class="#">Leia Mais >></a>
		</p>
	</div>
	

Na página SOBRE apenas foram adicionados textos utilizando cod div p h1 e style="margin" para dar formatação da margem dos textos adicionados.


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
	
Na pagina PORTIFOLIO utilizei o javascript para criar o meu slideshow scriptado com a função fade e velocidade de 2s.
Utilizando jquery.cycle.all e jquery.min
http://jquery.malsup.com/cycle/
http://jquery.com/

<!--------SCRIPT-------> portfolio.html
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

<!--------------COD DAS IMG SCRIPTADAS POR JAVASCRIPT-----> portfolio.html
	<div class="slides">
			<ul>
				<li> <img src="img/imagem1.jpg" alt="Slide 1" width="1347" height="400" /> </li>
				<li> <img src="img/lorem1.jpg" alt="Slide 2" width="1347" height="400" /> </li>
				<li> <img src="img/lorem2.png" alt="Slide 3" width="1347" height="400" /> </li>
				<li> <img src="img/lorem3.jpg" alt="Slide 4" width="1347" height="400" /> </li>
			</ul>
	</div>
	

Na parte de requisição e validação de dados passei a utilizar o nodepad++ para poder ao tempo que criava o corpo conseguisse testar em mais de um navegador de forma mais ágil.
A criação do formulário se baseia em na seguinte estrutura:

<!------COD FORMULÁRIO-------> contato.html

	<form method="poster" action="gravar.html">
		<label> Nome: </label><br>
			<input type="text" required class="campo" id="nome" /><br>
		<label> Email: </label><br>
			<input type="email" placeholder="name@email.com" required class="campo" id="email" /><br>
		<label> Telefone: </label><br>
			<input type="tel" id="phonenum" type="tel" placeholder="Ex 48 89879-3323" pattern="^\d{2} \d{5}-\d{4}$" required class="campo" id="telefone" /><br>
		<label> Assunto: </label><br>
		<textarea type="textAssunto" cols="30" placeholder="Não é obrigatório" rows="6" > </textarea><br>
	
		<input  class="button" type="submit"/>
					
					
	</form>
	
Utilizando a chave FORM com o comando POSTER para enviar a um site de hospedagem e a ACTION para selecionar o domínio qual o usuário seria encaminhado.
utilizando o comando REQUIRED dentro do INPUT para fazer com que o campo desejado seja obrigatório, além de outros artefatos tanto para email como também numero de telefone com a chave TYPE para permitir entradas que fossem desejadas como email valido e número de telefone contendo apenas algarismos numéricos.
Com o cmd INPUT editei meu clickbox da pagina. Utilizando o CSS dei vida para o formulário, criando sombras, bordas animações com botões mouse e cores para deixar o site mais moderno permitindo se adequar o visual de ambas as páginas. 

<!-------------CMD FORMULÁRIO CSS------> style.css

	.button{
		background:#ff8a00;
		border:20;
		padding:10px;
		width:110px;
		border-radius:5px;
		cursor:pointer;

	}
Permitindo animar o cursos ao passar por cima da checkbox e mudar visual, tamanho, borda etc..

	.button:hover{
		background-color:#FF5105;
	}
Com o cmd HOVER é feita a animação com alteração de cor ao passar o mouse sobre uma checkbox
	
	#formulario label{
		float:left;
O cmd LABEL para utilizar a ordem FLOAT permitindo que todos os campos do meu formulario se alinhassem a sua esquerda, não permitindo os campos de ficarem tortos na pagina de web.


Para a página de confirmação apenas linkei a minha página de formulário com uma hiperlink para poder retornar.

<!------CMD PG CONFIRMAÇÃO------->

	<div class="conteudo">
	<p>
		Parabéns! Seu cadastro já foi concluído!!

		Se deseja retornar, clique no botão voltar.
	</p>
		<div>
		<p>
			<a href="contato.html" id="bntInfo" class="#"><< Voltar </a>
		</p>
		</div>
	</div>


SITE CONCLUÍDO. :)


