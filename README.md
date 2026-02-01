# 📝 ASP.NET Core MVC - Formulários

<div align="center">

![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-8.0-512BD4?style=for-the-badge&logo=.net&logoColor=white)
![C#](https://img.shields.io/badge/C%23-12.0-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3.2-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**Projeto educacional demonstrando três métodos diferentes para trabalhar com formulários em ASP.NET Core MVC**

[Demonstração](#-demonstração) •
[Funcionalidades](#-funcionalidades) •
[Instalação](#-instalação) •
[Uso](#-uso) •
[Documentação](#-documentação)

</div>

---

## 📖 Sobre o Projeto

Este projeto foi desenvolvido com fins **educacionais** para demonstrar as melhores práticas no desenvolvimento de aplicações web ASP.NET Core MVC, focando especificamente em três abordagens diferentes para criar e processar formulários web.

### 🎯 Objetivos de Aprendizagem

- ✅ Criar e configurar projetos ASP.NET Core MVC
- ✅ Implementar Controllers e Actions (GET/POST)
- ✅ Desenvolver Views com Razor Syntax
- ✅ Trabalhar com diferentes métodos de envio de formulários
- ✅ Aplicar validação de dados (client-side e server-side)
- ✅ Utilizar Data Annotations
- ✅ Implementar design responsivo com Bootstrap
- ✅ Seguir o padrão MVC (Model-View-Controller)

---

## ✨ Funcionalidades

### 🔹 Três Métodos de Formulários

#### 1️⃣ **Form 1 - Parâmetros como Variáveis**
- Recebe cada campo do formulário como um parâmetro individual
- Ideal para formulários simples e pequenos
- Exemplo: Formulário de login

```csharp
[HttpPost]
public ActionResult Form_1(string utilizador, string password, string? lembrar)
{
    // Processar dados...
}
```

#### 2️⃣ **Form 2 - FormCollection**
- Utiliza `IFormCollection` para receber todos os campos
- Útil para formulários com muitos campos ou dinâmicos
- Exemplo: Formulário de registo

```csharp
[HttpPost]
public ActionResult Form_2(IFormCollection formCollection)
{
    string nome = formCollection["Nome"];
    // Processar dados...
}
```

#### 3️⃣ **Form 3 - Model Binding** ⭐ *Recomendado*
- Usa Model Binding com Data Annotations
- Validação automática server-side e client-side
- Type-safe e código mais limpo
- Exemplo: Formulário completo com validação

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public IActionResult Form_3(Cliente cliente)
{
    if (ModelState.IsValid)
    {
        // Processar dados válidos...
    }
    return View(cliente);
}
```

---

## 🖼️ Demonstração

### Página Inicial
![Home Page](https://via.placeholder.com/800x400/0d6efd/ffffff?text=Página+Inicial+com+3+Cards)

### Form 3 - Model Binding com Validação
![Form 3](https://via.placeholder.com/800x400/dc3545/ffffff?text=Formulário+com+Validação)

### Dados Recebidos
![Dados Recebidos](https://via.placeholder.com/800x400/198754/ffffff?text=Dados+Recebidos+com+Sucesso)

---

## 🚀 Instalação

### Pré-requisitos

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- [Visual Studio 2022](https://visualstudio.microsoft.com/) (ou VS Code)
- [Git](https://git-scm.com/)

### Passos de Instalação

1. **Clone o repositório**
```bash
git clone https://github.com/seu-usuario/asp-net-core-forms.git
cd asp-net-core-forms
```

2. **Restaure os pacotes NuGet**
```bash
dotnet restore
```

3. **Execute a aplicação**
```bash
dotnet run
```

4. **Aceda no browser**
```
https://localhost:5001
```

### Usando Visual Studio

1. Abra o ficheiro `ASP_NET_Core_Forms.csproj`
2. Pressione `F5` para executar
3. O browser abrirá automaticamente

---

## 💻 Uso

### Estrutura do Projeto

```
ASP_NET_Core_Forms/
│
├── Controllers/
│   └── HomeController.cs          # Controller principal
│
├── Models/
│   └── Cliente.cs                 # Modelo com Data Annotations
│
├── Views/
│   ├── Home/
│   │   ├── Index.cshtml          # Página inicial
│   │   ├── Form_1.cshtml         # Formulário método 1
│   │   ├── Form_2.cshtml         # Formulário método 2
│   │   ├── Form_3.cshtml         # Formulário método 3
│   │   ├── Dados_recebidos.cshtml # Exibição de dados
│   │   ├── Sobre.cshtml          # Informações do projeto
│   │   └── Conteudo.cshtml       # Conteúdo programático
│   │
│   ├── Shared/
│   │   ├── _Layout.cshtml        # Layout principal
│   │   └── _ValidationScriptsPartial.cshtml
│   │
│   ├── _ViewStart.cshtml
│   └── _ViewImports.cshtml
│
├── wwwroot/
│   ├── css/
│   │   └── site.css              # Estilos personalizados
│   └── js/
│       └── site.js               # JavaScript
│
├── Program.cs                     # Configuração da aplicação
└── appsettings.json
```

### Testando os Formulários

#### 📝 Form 1 - Login Simples
1. Navegue para `/Home/Form_1`
2. Preencha utilizador e password
3. Opcionalmente marque "Lembrar"
4. Clique em "Entrar"

#### 📝 Form 2 - Registo
1. Navegue para `/Home/Form_2`
2. Preencha Nome, Apelido e Email
3. Clique em "Enviar Dados"

#### 📝 Form 3 - Validação Completa
1. Navegue para `/Home/Form_3`
2. **Teste validação**: Deixe campos vazios
3. **Teste email**: Digite email inválido
4. **Teste password**: Digite menos de 4 caracteres
5. Preencha corretamente e envie

---

## 🛠️ Tecnologias Utilizadas

<div align="center">

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| **ASP.NET Core** | 8.0 | Framework web |
| **C#** | 12.0 | Linguagem de programação |
| **Razor** | - | View engine |
| **Bootstrap** | 5.3.2 | Framework CSS |
| **Bootstrap Icons** | 1.11.1 | Ícones |
| **jQuery** | 3.7.1 | Validação client-side |
| **jQuery Validation** | 1.19.5 | Validação de formulários |

</div>

---

## 📚 Documentação

### Data Annotations Utilizadas

```csharp
public class Cliente
{
    [Required(ErrorMessage = "Nome obrigatório")]
    [Display(Name = "Nome do Utilizador")]
    public string Nome { get; set; }

    [Required(ErrorMessage = "Email obrigatório")]
    [StringLength(100, ErrorMessage = "Máximo 100 caracteres")]
    [EmailAddress(ErrorMessage = "Email inválido!")]
    public string Email { get; set; }

    [StringLength(10, MinimumLength = 4)]
    [DataType(DataType.Password)]
    public string Password { get; set; }
}
```

### Tag Helpers Principais

```html
<!-- Form -->
<form asp-action="Form_3" method="post">

<!-- Input vinculado ao modelo -->
<input asp-for="Nome" class="form-control" />

<!-- Mensagem de validação -->
<span asp-validation-for="Nome" class="text-danger"></span>

<!-- Link para action -->
<a asp-action="Index" asp-controller="Home">Voltar</a>
```

### Rotas Configuradas

| Rota | Controller | Action | Descrição |
|------|-----------|--------|-----------|
| `/` | Home | Index | Página inicial |
| `/Home/Form_1` | Home | Form_1 | Formulário método 1 |
| `/Home/Form_2` | Home | Form_2 | Formulário método 2 |
| `/Home/Form_3` | Home | Form_3 | Formulário método 3 |
| `/Home/Sobre` | Home | Sobre | Sobre o projeto |
| `/Home/Conteudo` | Home | Conteudo | Conteúdo programático |

---

## 🎨 Design e UI/UX

### Características do Design

- ✨ **Responsivo**: Funciona em desktop, tablet e mobile
- 🎨 **Bootstrap 5**: Design moderno e profissional
- 🔄 **Animações**: Transições suaves nos cards e botões
- 📱 **Mobile-First**: Otimizado para dispositivos móveis
- 🎯 **Acessível**: Navegação intuitiva
- 🌈 **Cores**: Esquema de cores consistente

### Paleta de Cores

| Uso | Cor | Hex |
|-----|-----|-----|
| Primária | Azul | `#0d6efd` |
| Sucesso | Verde | `#198754` |
| Perigo | Vermelho | `#dc3545` |
| Fundo | Cinza Claro | `#f8f9fa` |
| Navbar | Cinza Escuro | `#343a40` |

---

## 🔒 Segurança

### Medidas Implementadas

- ✅ **Anti-Forgery Tokens**: Proteção contra CSRF
- ✅ **Validação Server-Side**: Todos os dados validados no servidor
- ✅ **HTTPS**: Comunicação encriptada (em produção)
- ✅ **Input Validation**: Prevenção de injection attacks
- ✅ **Model Binding**: Type-safe data binding

```csharp
[HttpPost]
[ValidateAntiForgeryToken] // Proteção CSRF
public IActionResult Form_3(Cliente cliente)
{
    if (ModelState.IsValid) // Validação server-side
    {
        // Código seguro...
    }
}
```

---

## 📊 Validações Implementadas

### Form 3 - Validações Completas

| Campo | Validações |
|-------|-----------|
| **Nome** | Obrigatório |
| **Apelido** | Opcional |
| **Email** | Obrigatório, formato válido, máx. 100 caracteres |
| **Password** | Mínimo 4 caracteres, máximo 10 caracteres |

### Validação Client-Side

```javascript
// jQuery Validation (automático via Tag Helpers)
<script src="jquery.validate.min.js"></script>
<script src="jquery.validate.unobtrusive.min.js"></script>
```

### Validação Server-Side

```csharp
if (ModelState.IsValid)
{
    // Processar dados válidos
}
else
{
    // Retornar erros para o utilizador
    return View(cliente);
}
```

---


### Funcionalidades Futuras

- [ ] Integração com Entity Framework Core
- [ ] CRUD completo de clientes
- [ ] Autenticação e autorização (Identity)
- [ ] Upload de ficheiros
- [ ] API REST
- [ ] Testes unitários
- [ ] Docker support
- [ ] CI/CD Pipeline

---


## 👨‍💻 Autor

**Seu Nome**

- GitHub: [Nicogowork](https://github.com/seu-usuario](https://github.com/Nicogowork)
  
---

## 🙏 Agradecimentos

- [ASP.NET Core Documentation](https://docs.microsoft.com/aspnet/core)
- [Bootstrap Documentation](https://getbootstrap.com/docs/)
- [Microsoft Learn](https://learn.microsoft.com/)
- Comunidade .NET

---


## 🌟 Se Gostou do Projeto

Se este projeto foi útil para você, considere:

- ⭐ Dar uma **estrela** no repositório
- 🍴 Fazer um **fork** para suas próprias experiências
- 📢 **Compartilhar** com outros desenvolvedores
- 💬 Deixar **feedback** ou sugestões

---

<div align="center">

**Desenvolvido com ❤️ para fins educacionais**

![ASP.NET Core](https://img.shields.io/badge/Made%20with-ASP.NET%20Core-512BD4?style=flat-square&logo=.net)
![Bootstrap](https://img.shields.io/badge/Styled%20with-Bootstrap-7952B3?style=flat-square&logo=bootstrap)

[⬆ Voltar ao topo](#-aspnet-core-mvc---formulários)

</div>
