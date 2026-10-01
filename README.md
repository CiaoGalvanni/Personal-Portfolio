# Portfólio | Leonardo Pinheiro

Portfólio pessoal de **João Pedro Leonardo Pinheiro** (Leonardo), estudante de Análise e Desenvolvimento de Sistemas na UNICEUMA, em São Luís, Maranhão. Desenvolvido como atividade acadêmica.

O site inteiro é um único arquivo HTML, sem framework e sem etapa de build.

## Destaques

- **Trajetória do sol em tempo real:** o topo da página desenha o caminho do sol sobre São Luís no dia atual, com a posição de agora, a elevação e o azimute. O cálculo é feito no navegador e atualiza a cada minuto.
- **Quatro idiomas:** português (padrão), inglês, espanhol e francês. A escolha fica salva no navegador.
- **Tema claro e escuro:** segue automaticamente a preferência do sistema.
- **Responsivo:** funciona do celular ao desktop, respeitando as áreas seguras de telas com notch.
- **Acessibilidade:** link para pular ao conteúdo, foco visível, rótulos ARIA, contraste adequado e animação desativada quando o sistema pede movimento reduzido.

## Projetos apresentados

| Projeto | Área | Contexto |
|---|---|---|
| Panel Monitoring System (PMS) | Energia | Produto próprio, em uso por uma empresa de energia solar |
| Helios | Energia | Desafio EDX Capital, hackathon TechX 2026 (Universidade Ceuma) |
| EDX Console | Energia | Ecossistema EDX Capital |
| HubSolo | Comércio digital | Projeto acadêmico em grupo, UNICEUMA |

## Como abrir

Basta abrir o arquivo HTML em qualquer navegador. Sem internet a página continua funcionando, só a fonte Archivo não carrega e o texto usa uma fonte sans-serif padrão.

Para servir localmente:

```bash
python -m http.server 8000
```

Depois acesse `http://localhost:8000/portfolio-leonardo-pinheiro.html`.

### Publicar no GitHub Pages

1. Renomeie o arquivo para `index.html` e envie para um repositório.
2. Em **Settings → Pages**, escolha a branch `main` e a pasta raiz.
3. O site fica disponível em `https://ciaogalvanni.github.io/<nome-do-repositorio>/`.

## Tecnologias

- HTML5 semântico
- CSS3 com variáveis, Grid, Flexbox e fonte variável (eixos de largura e peso)
- JavaScript puro
- SVG para a trajetória do sol
- [Archivo](https://fonts.google.com/specimen/Archivo), via Google Fonts

## Como editar

Todo o conteúdo fica no bloco `<script>` no final do arquivo.

### Contato

```js
const CONTACT = {
  email: "leozgpp@gmail.com",
  github: "https://github.com/CiaoGalvanni"
};
```

### Adicionar um projeto

Inclua um objeto na lista `PROJECTS`:

```js
{
  group: "energy",          // "energy" ou "commerce"
  featured: true,           // opcional: exibe o projeto em destaque
  status: "live",           // opcional: "live", "dev" ou "concept"
  name: "Nome do projeto",  // texto simples ou { pt, en, es, fr }
  context: { pt: "...", en: "...", es: "...", fr: "..." },
  desc:    { pt: "...", en: "...", es: "...", fr: "..." },
  stack: "Python, FastAPI"  // opcional
}
```

Para criar uma área nova, adicione o nome dela em `groups` dentro de cada idioma do objeto `UI` e inclua a chave na lista `["energy", "commerce"]` da função `renderProjects`.

### Adicionar um idioma

1. Copie um dos blocos do objeto `UI` (por exemplo, `pt`) com uma nova chave e traduza os textos.
2. Adicione a tradução em `context`, `desc` e, se houver, `name` de cada projeto.
3. Inclua um botão no cabeçalho: `<button type="button" data-lang="xx" aria-pressed="false">XX</button>`.

## Cálculo solar

A posição do sol usa as equações de posição solar da NOAA (equação do tempo, declinação e ângulo horário), com as coordenadas de São Luís (latitude −2,53°, longitude −44,30°, UTC−3). A precisão é suficiente para fins visuais, mas não para aplicações de engenharia.

## Autor

**João Pedro Leonardo Pinheiro**

- E-mail: [leozgpp@gmail.com](mailto:leozgpp@gmail.com)
- GitHub: [CiaoGalvanni](https://github.com/CiaoGalvanni)
