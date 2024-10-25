<h1 style="text-align: center;">POC 5 - Desenvolvimento com Next.js e React</h1>
<p>Wagner Junior | RA: 10440125</p>

## Estrutura do Projeto em Next.js (Versão 14 ou Superior)

Next.js, em conjunto com React, fornece uma estrutura eficiente para criar aplicações web, aproveitando a renderização no servidor para melhorar o tempo de resposta e a experiência do usuário. Para iniciar um projeto com Next.js, utilize o comando:

```bash
npx create-next-app@latest


Ao configurar o projeto, o assistente oferece algumas opções de personalização, como:

- Nome do projeto
- Escolha entre TypeScript ou JavaScript
- Uso do Tailwind CSS como framework de estilo
- Configuração do ESLint para padronizar o código
- E outros recursos opcionais

### Principais Arquivos

#### package.json

O package.json centraliza as configurações de scripts e dependências essenciais para o funcionamento do projeto. Ele inclui informações como a versão do Next.js e as instruções para iniciar, compilar e executar a aplicação. Exemplo:

    {
        "name": "poc-5",
        "version": "0.1.0", 
        "private": true,
        "scripts": {
            "dev": "next dev",
            "build": "next build",
            "start": "next start",
            "lint": "next lint"
        },
        "dependencies": {
            "react": "^18",
            "react-dom": "^18",
            "next": "14.2.15"
        }
    }

#### page.js

Este arquivo representa a página principal da aplicação. Ao iniciar um projeto, Next.js fornece uma página padrão, incluindo a logo do Next.js e links para a documentação.

#### layout.js

O layout.js define o layout básico e organiza elementos que devem ser comuns a todas as páginas da aplicação, como cabeçalhos e rodapés. Ele utiliza a estrutura {children} para representar o conteúdo de cada página específica. Exemplo:

    export default function RootLayout({ children }) {
      return (
       <html lang="en">
         <body>
           <HeaderComponent/>
           {children}
         </body>
       </html>
     );
    }

No exemplo, o componente HeaderComponent é carregado em todas as páginas antes do conteúdo específico definido pelo {children}. 

## Criação de Componentes Simples (Sem Estado)

Componentes básicos em React são funções que retornam um layout JSX. O exemplo abaixo mostra a criação de um cabeçalho (HeaderComponent), que inclui links de navegação:

    export default function HeaderComponent(){
    return (
        <header className={styles.header}>
            <h1 className={styles.title}>Blog</h1>
            <div className={styles.container}>
                <Link href="/" className={styles.redirects}>Home</Link>
                <Link href="/about" className={styles.redirects}>About</Link>
                <Link href="/contact" className={styles.redirects}>Contact</Link>
            </div>
        </header>
    );    
}

Este componente é um cabeçalho que exibe o título "Meu Blog" e possui links para navegar entre as páginas "Início", "Sobre" e "Contato".

## Estilo CSS (Global e Módulo)

### CSS Global

O arquivo globals.css é utilizado para definir estilos que serão aplicados em toda a aplicação, como fontes, cores de fundo e margens:


    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }

### CSS Módulo

Módulos CSS permitem que estilos específicos sejam aplicados a um componente individual, isolando-os para evitar que afetem outros componentes. Abaixo está um exemplo de módulo CSS para estilizar o HeaderComponent:

    .header {
        background-color: black;
        color: red;
        display: flex;
        flex-direction: column;
    }

    .container {
        display: flex;
        justify-content: space-evenly;
        padding: 1rem;
    }

    .redirects {
        color: blue;
        text-decoration: none;
        margin: 0 1rem;
        border-style: solid;
        border-width: 1px;
        border-color: red;
    }

    .title {
        color: red;
        text-align: center;
    }

Com essa configuração, o projeto Next.js com React é estruturado com componentes reutilizáveis e estilos modulares, proporcionando uma aplicação de fácil manutenção e visualmente organizada.

 
