A "index.html" é a parte de criação de conta, onde o usuário  criará susa conta para efetuar seu login

A "login.html" é a aba onde o usuário irá efetuar seu login após criar sua conta

A "home.html" é a pagina inicial do site, onde o usua-ário irá navegar entre as informações disponiveis nele

A "script.js" é a parte onde se encontra o JavaScript do site, responsavel pelo funcionamento das funções de criação de conta e login

A "style.css" é a parte onde se encontra o css do site, responsavel pela parte visual dele

As paginas "carro.html", "livro.html" e "robo.html" são paginas que podem ser alcançadas a partir da home e possuem informações sobre a proposta do site, de mostrar a visão do futuro que as pessoas do passado possuiam.


//Salva as informações de loggin no localStorage
function SalvarN() {
    let nome = document.getElementById('nome').value
    localStorage.setItem('nomeUsuario', nome);

    let email = document.getElementById('email').value
    localStorage.setItem('emailUsuario', email);

    let senha = document.getElementById('senha').value
    localStorage.setItem('senhaUsuario', senha,);

   


    //var login =  {nome: nome, email: email, senha: senha}

    //login_json = JSON.stringify(login);

    //localStorage.setItem('loginUsuario', login_json);

    //localStorage.setItem('emailUsuario', email);


    //localStorage.setItem('senhaUsuario', senha,);

} 

//resgata as informações de login para logar na conta
function Login() {
    let nomeArmazenado =  localStorage.getItem('nomeUsuario');
    let emailArmazenado =  localStorage.getItem('nomeUsuario');
    let senhaArmazenado =  localStorage.getItem('nomeUsuario');
    let nomeLogin = document.getElementById('nomeL');
    let emailLogin = document.getElementById('emailL');
    let senhaLogin = document.getElementById('senhaL');
    //let Nlogin = [nomeLogin, emailLogin, senhaLogin];
    if ((nomeArmazenado = nomeLogin) && (emailArmazenado = emailLogin) && (senhaArmazenado = senhaLogin)) {
        window.location.href = "home.html";
        e.preventDefault()
    } else {
        alert("epa");
        e.preventDefault()
    }
}









//Código para logout do usuário

document.addEventListener("DOMContentLoaded", function () {
    const logoutLink = document.getElementById("logout");

    if (logoutLink) {
        logoutLink.addEventListener("click", function (event) {
            event.preventDefault(); 
            const usuarioLogado = localStorage.getItem("usuarioLogado");

            if (usuarioLogado) {
              
                localStorage.removeItem("usuarioLogado");

               
                alert("Você foi deslogado!!!");

            } else {
                
                alert("Você não está logado!!!");
            }
        });
    }
});