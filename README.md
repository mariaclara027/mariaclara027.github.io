<div align="center">

<img src="img/icon-512.png" alt="Enf. Maria Clara" width="104" height="104">

# Enf. Maria Clara · Enfermagem Domiciliar

**Cuidado de enfermagem no conforto da sua casa — Várzea Grande e Cuiabá / MT**

Landing page de página única para captação de pacientes via WhatsApp.

[![Site no ar](https://img.shields.io/badge/site-mariaclara027.github.io-14A39B?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mariaclara027.github.io/)
[![GitHub Pages](https://img.shields.io/badge/deploy-GitHub%20Pages-0B6E6A?style=for-the-badge&logo=github&logoColor=white)](https://pages.github.com/)
[![WhatsApp](https://img.shields.io/badge/contato-(65)%2098105--4265-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/5565981054265)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/Vanilla%20JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Sem build](https://img.shields.io/badge/build-nenhum-success?style=flat-square)
![Dependências](https://img.shields.io/badge/depend%C3%AAncias-0-success?style=flat-square)

</div>

---

## ✦ Sobre o projeto

Site institucional da enfermeira **Maria Clara Alves de Oliveira**, que presta atendimento
domiciliar em Várzea Grande e Cuiabá. O objetivo é simples e único: **transformar uma visita
no site em uma conversa no WhatsApp**.

Tudo cabe em um arquivo. Sem framework, sem `npm install`, sem etapa de build — é só abrir o
`index.html` no navegador ou dar `git push` para publicar.

<table>
<tr>
<td width="50%" valign="top">

**🩺 Para a paciente / família**
- Serviços explicados sem jargão
- Botão de WhatsApp sempre à mão
- Formulário que já monta a mensagem pronta
- Dúvidas frequentes respondidas
- Aviso claro de emergência (SAMU 192)

</td>
<td width="50%" valign="top">

**⚙️ Para quem mantém**
- Um arquivo, zero dependências
- Número e nome em um único bloco `CONFIG`
- SEO local e dados estruturados prontos
- Geradores de imagem inclusos
- Deploy = `git push`

</td>
</tr>
</table>

---

## ✦ Estrutura

```
mariaclara027.github.io/
│
├── index.html          ← o site inteiro (HTML + CSS + JS inline, ~1.000 linhas)
├── icon.html           ← gerador do ícone 512×512  (não indexado)
├── og-image.html       ← gerador do card 1200×630  (não indexado)
│
├── img/
│   ├── enfermeira.png          foto do hero e da seção "Sobre" (PNG sem fundo)
│   ├── enfermeira-original.png backup da foto original
│   ├── icon-512.png            ícone para "adicionar à tela inicial"
│   └── og-cover.jpg            imagem que aparece ao compartilhar o link
│
├── robots.txt          ← libera o site, bloqueia os geradores
├── sitemap.xml         ← uma URL, a raiz
└── README.md
```

---

## ✦ Seções da página

| # | Seção | O que entrega |
|:-:|-------|---------------|
| 1 | **Hero** | Proposta de valor, dois CTAs e cartão flutuante com um "plano de cuidados" de exemplo |
| 2 | **Números** | Formação (UNIVAG), UTI/urgência e emergência (ESTETUS) e experiência em paliativos |
| 3 | **Serviços** | 6 cards — cada um com link direto para o WhatsApp já com o assunto escrito |
| 4 | **Sobre** | Trajetória profissional e o jeito de trabalhar |
| 5 | **Como funciona** | Contato → avaliação e plano de cuidados → visitas |
| 6 | **Dúvidas** | 5 perguntas em `<details>` — plano de saúde, região, horários, prescrição, cobrança |
| 7 | **Contato** | Formulário + dados diretos + alerta de emergência |

---

## ✦ Como rodar

O site é estático puro. Abrir o arquivo já funciona:

```bash
# opção 1 — direto no navegador
start index.html          # Windows
```

```bash
# opção 2 — servidor local (recomendado, evita esquisitices de file://)
python -m http.server 8000
# → http://localhost:8000
```

---

## ✦ Como editar

### 📱 Trocar o número do WhatsApp

Um lugar só, no fim do [index.html](index.html#L947). Todos os botões, links do rodapé e o
formulário passam a usar o novo número automaticamente:

```js
const CONFIG = {
  whatsapp: "5565981054265",   // DDI + DDD + número, só dígitos
  nome: "Maria Clara",
  mensagemPadrao: "Olá, Maria Clara! Vi seu site e gostaria de agendar um atendimento..."
};
```

> O número exibido em texto é formatado sozinho — qualquer elemento com `data-wa-display`
> recebe `(65) 98105-4265` sem você digitar nada.

<details>
<summary><b>📷 Trocar a foto</b></summary>

<br>

Substitua `img/enfermeira.png` — **PNG sem fundo**, algo próximo de 900×1100.
Se o arquivo não existir, o site mostra uma silhueta ilustrativa no lugar, sem quebrar o layout.

</details>

<details>
<summary><b>🖼️ Regerar a imagem de compartilhamento (WhatsApp / Facebook)</b></summary>

<br>

1. Abra `og-image.html` no Chrome
2. `Ctrl+Shift+P` → **Capture screenshot**, com a janela em **1200×630**
3. Salve como `img/og-cover.jpg`
4. **Importante:** no `index.html`, troque `?v=1` por `?v=2` nas duas tags `og:image` —
   é isso que faz o WhatsApp largar a imagem antiga do cache

O mesmo vale para `icon.html`, capturado em **512×512** e salvo como `img/icon-512.png`.

</details>

<details>
<summary><b>🎨 Mudar as cores</b></summary>

<br>

Todas as cores são variáveis CSS em `:root`, no topo do `<style>`:

| Token | Valor | Uso |
|-------|-------|-----|
| `--teal-500` | `#14A39B` | Cor principal — botões, ícones, destaques |
| `--teal-700` | `#0B6E6A` | Textos e fundos escuros |
| `--teal-100` | `#D6F1EE` | Fundos suaves, seleção de texto |
| `--mint-50`  | `#F1FAF8` | Seções alternadas |
| `--ink`      | `#12262C` | Títulos |
| `--slate`    | `#5F737A` | Texto de apoio |
| `--coral`    | `#FF6B85` | Detalhe de contraste |
| `--wa`       | `#25D366` | Verde do WhatsApp |

Tipografia: **Outfit** nos títulos, **Nunito Sans** no corpo (Google Fonts).

</details>

<details>
<summary><b>🪪 Incluir o registro no COREN quando sair</b></summary>

<br>

Quatro pontos a atualizar:

1. Lista `.proof` do hero
2. Chip da seção **Sobre**
3. Rodapé
4. Campo `identifier` no bloco JSON-LD

</details>

---

## ✦ Detalhes técnicos

<table>
<tr><td width="34%"><b>Conversão</b></td><td>

Links com `data-wa` viram `wa.me/...` com mensagem pré-escrita. O formulário não envia
para servidor nenhum: ele monta nome, telefone, bairro, serviço e situação em uma
mensagem formatada e abre o WhatsApp.

</td></tr>
<tr><td><b>SEO</b></td><td>

Canonical, meta geo (BR-MT), Open Graph e Twitter Card completos, `sitemap.xml` e
`robots.txt`. Dados estruturados JSON-LD com `MedicalBusiness` + `LocalBusiness`,
`Person`, `WebSite`, `OfferCatalog` com os 6 serviços e `FAQPage` com as 5 perguntas —
elegível para rich results no Google.

</td></tr>
<tr><td><b>Acessibilidade</b></td><td>

HTML semântico, `:focus-visible` visível em tudo, `aria-label` / `aria-expanded` no menu,
labels reais em todos os campos e contraste dentro do padrão AA.

</td></tr>
<tr><td><b>Performance</b></td><td>

Zero requisições de JS ou CSS externo — só as fontes do Google, com `preconnect`.
Ícones são `<symbol>` SVG inline reaproveitados via `<use>`.

</td></tr>
<tr><td><b>Interações</b></td><td>

Header com sombra ao rolar, menu mobile, animações de entrada com `IntersectionObserver`
(com fallback), botão flutuante do WhatsApp e ano do rodapé automático.

</td></tr>
</table>

---

## ✦ Deploy

Hospedado no **GitHub Pages** a partir do branch `main`:

```bash
git add .
git commit -m "Atualiza a landing page"
git push
```

Em cerca de um minuto o site está no ar em **https://mariaclara027.github.io/**.

---

## ✦ Contato

<div align="center">

[![WhatsApp](https://img.shields.io/badge/WhatsApp-(65)%2098105--4265-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/5565981054265)
[![E-mail](https://img.shields.io/badge/E--mail-mariaclaraoliver027@gmail.com-14A39B?style=for-the-badge&logo=gmail&logoColor=white)](mailto:mariaclaraoliver027@gmail.com)

**Maria Clara Alves de Oliveira** · Enfermeira
Atendimento domiciliar em Várzea Grande e Cuiabá — MT

</div>

> [!WARNING]
> Este site **não substitui atendimento médico de urgência**.
> Em emergências, ligue **192** (SAMU) ou procure o pronto-socorro mais próximo.

<div align="center">
<sub>© 2026 Maria Clara Alves de Oliveira · Todos os direitos reservados</sub>
</div>
