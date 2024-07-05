/* Estilos CSS */
/* Estilos do login */
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
.login-container {
    background-color: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
}
input[type="text"],
input[type="password"] {
    width: 100%;
    padding: 10px;
    margin: 5px 0;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}
input[type="submit"] {
    background-color: #4caf50;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    width: 100%;
}
input[type="submit"]:hover {
    background-color: #45a049;
}

/* Estilos da tela após o login */
.after-login {
    display: none; /* Oculta a tela por padrão */
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.9); /* Fundo semi-transparente preto */
    z-index: 9999; /* Garante que a tela apareça acima de todos os outros elementos */
    color: white; /* Texto branco */
}
.after-login-content {
    background-color: #333; /* Fundo escuro */
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    width: 300px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
.after-login-content h2 {
    margin: 0;
    padding: 0 0 10px;
    font-size: 18px;
    text-align: center;
}
.after-login-content .option {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 10px 0;
}
.after-login-content .option label {
    margin-right: 10px;
}
.after-login-content .option input[type="checkbox"] {
    appearance: none;
    width: 40px;
    height: 20px;
    background: #444;
    border-radius: 10px;
    position: relative;
    outline: none;
    cursor: pointer;
    transition: background 0.3s;
}
.after-login-content .option input[type="checkbox"]:checked {
    background: #ff4500;
}
.after-login-content .option input[type="checkbox"]:before {
    content: '';
    position: absolute;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: #fff;
    top: 1px;
    left: 1px;
    transition: transform 0.3s;
}
.after-login-content .option input[type="checkbox"]:checked:before {
    transform: translateX(20px);
}
.account-info {
    margin-top: 20px;
}
.account-info p {
    margin: 5px 0;
}
.account-info p span {
    font-weight: bold;
}
.bypass-button {
    margin-top: 20px;
    text-align: center;
}
.bypass-button button {
    background-color: #555;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
.bypass-button button:hover {
    background-color: #777;
}
