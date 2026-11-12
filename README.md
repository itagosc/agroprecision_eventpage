# Agroprecision — Agenda de eventos

Site aberto e sem fins lucrativos do grupo de pesquisa **Agroprecision**. Reúne congressos, simpósios, feiras e encontros técnicos em três carrosséis, com busca em tempo real.

- Sem login e sem coleta de dados dos visitantes.
- HTML5 + [Tailwind CSS](https://tailwindcss.com) (via CDN) + JavaScript puro. Não há instalação nem etapa de build.
- Todos os eventos vêm do arquivo [`eventos.json`](eventos.json). **Para adicionar ou alterar um evento, você só edita esse arquivo.**
- Hospedagem gratuita no GitHub Pages.

---

## Estrutura do projeto

```
/
├── index.html      → o site (layout, estilos e lógica)
├── eventos.json    → a lista de eventos (o único arquivo que os membros editam)
├── logo.png        → logo do grupo
├── imagens/        → fotos/capas dos eventos (opcional)
└── README.md       → este guia
```

---

## Como adicionar um novo evento (passo a passo, sem programar)

Você vai precisar de uma conta gratuita no GitHub e de permissão de edição no repositório (peça ao responsável do grupo para te adicionar como colaborador).

### Passo 1 — Abra o arquivo `eventos.json`
No repositório, clique em **`eventos.json`**. Depois clique no ícone de **lápis** (✏️ *Edit this file*) no canto superior direito.

### Passo 2 — Copie o molde
Copie o bloco abaixo (de `{` até `}`):

```json
{
  "id": "",
  "titulo": "",
  "categoria": "",
  "data": "",
  "submissao": "",
  "local": "",
  "modalidade": "",
  "resumo": "",
  "imagem": "",
  "link": ""
}
```

> **Ordem dos cards:** o site ordena sozinho cada carrossel pela data mais próxima de hoje. Escreva a data com o ano (ex.: `"17 de nov. de 2026"` ou `"25 a 28 de abr. de 2027"`). Eventos com "Data a confirmar" ficam depois dos datados, e os já realizados vão para o fim.

### Passo 3 — Cole o molde no lugar certo
Role até o **fim da lista**. O último evento termina com `}` e logo depois vem `]`. Siga esta regra:

1. Coloque uma **vírgula** depois do `}` do último evento.
2. Cole o molde logo abaixo.
3. O **último** bloco da lista **não** leva vírgula.

Exemplo (dois eventos):

```json
[
  {
    "id": "evento-um",
    "titulo": "Primeiro evento",
    ...
    "link": "https://exemplo.com"
  },                              ← vírgula aqui, porque vem outro evento depois
  {
    "id": "evento-dois",
    "titulo": "Segundo evento",
    ...
    "link": "https://exemplo.com"
  }                               ← SEM vírgula, é o último
]
```

### Passo 4 — Preencha os campos
Escreva **entre as aspas**. Veja o que vai em cada campo:

| Campo | O que escrever | Exemplo |
|---|---|---|
| `id` | Um nome único, sem espaços nem acentos, com hífens. Não pode repetir. | `"cbrg-2026"` |
| `titulo` | Nome do evento. | `"Congresso Brasileiro de Recursos Genéticos"` |
| `categoria` | **Exatamente** uma destas três (veja a observação abaixo). | `"Congressos e simpósios"` |
| `data` | Texto livre: dia ou período. | `"10 a 13 de nov. de 2026"` |
| `submissao` | **Opcional.** Prazo para enviar trabalhos. Aparece no card como "Submissão: ...". Se o evento não tiver, deixe `""` e a linha não aparece. | `"até 15 de jul. de 2026"` |
| `local` | Cidade/Estado ou instituição. | `"Florianópolis - SC"` |
| `modalidade` | **Exatamente** `"Presencial"`, `"Online"` ou `"Híbrido"`. | `"Presencial"` |
| `resumo` | Descrição curta (1 a 2 frases). | `"Congresso nacional sobre..."` |
| `imagem` | Caminho de uma imagem da pasta `imagens/` **ou** um link de imagem. Pode ficar `""` (o site mostra uma capa verde padrão). | `"imagens/cbrg-2026.jpg"` |
| `link` | Endereço oficial do evento, começando com `https://`. | `"https://cbrg.com.br/"` |

**Categorias aceitas** (copie e cole, com a mesma grafia, maiúsculas e acentos):

- `UFVJM`
- `Congressos e simpósios`
- `Feiras e encontros`

### Passo 5 — Salve (commit)
Clique em **Commit changes…** (botão verde no canto superior direito), escreva uma frase curta como `Adiciona evento CBRG 2026` e confirme em **Commit changes**.

### Passo 6 — Confira o site
Em 1 a 2 minutos o GitHub Pages atualiza. Abra o site e use **Ctrl + F5** (ou puxe a tela para baixo no celular) para recarregar sem cache.

> Se o evento não aparecer, veja a seção [Problemas comuns](#problemas-comuns).

---

## Molde em branco (copie e cole)

```json
{
  "id": "",
  "titulo": "",
  "categoria": "",
  "data": "",
  "submissao": "",
  "local": "",
  "modalidade": "",
  "resumo": "",
  "imagem": "",
  "link": ""
}
```

### Exemplo preenchido

```json
{
  "id": "cbrg-2026",
  "titulo": "Congresso Brasileiro de Recursos Genéticos (CBRG)",
  "categoria": "Congressos e simpósios",
  "data": "10 a 13 de nov. de 2026",
  "submissao": "até 15 de jul. de 2026",
  "local": "Florianópolis - SC",
  "modalidade": "Presencial",
  "resumo": "Congresso nacional sobre conservação e uso de recursos genéticos vegetais, animais e de microrganismos.",
  "imagem": "imagens/cbrg-2026.jpg",
  "link": "https://cbrg.com.br/"
}
```

---

## Como adicionar a imagem de capa (opcional)

**Opção A — Enviar a imagem para o repositório (recomendado)**
1. Abra a pasta `imagens/` no GitHub.
2. Clique em **Add file → Upload files**, arraste a imagem e faça o commit.
3. No evento, escreva o caminho: `"imagem": "imagens/nome-da-imagem.jpg"`.
   (O nome precisa ser igual ao do arquivo, incluindo maiúsculas e a extensão.)

**Opção B — Usar um link de imagem**: cole o endereço completo (`https://...jpg`).

Dicas: use imagens horizontais (proporção 16:9), com até ~300 KB, e **só use imagens que você tem direito de divulgar** (de preferência a arte oficial do próprio evento).

Para **não usar imagem**, deixe `"imagem": ""`.

---

## Regras de ouro do JSON (evitam 99% dos erros)

1. Use **aspas duplas** `"` (nunca aspas "curvas" `“ ”` de Word/WhatsApp).
2. **Vírgula** entre os campos e entre os eventos, **menos no último**.
3. Cada campo tem o formato `"nome": "valor"`.
4. Se o texto tiver aspas por dentro, escreva `\"` (ou troque por aspas simples).
5. Não deixe nenhum campo de fora (só `imagem` pode ser `""`).
6. A lista inteira fica entre `[` e `]`.

> Dica: antes de salvar, cole o conteúdo em <https://jsonlint.com> para verificar se está correto.

---

## Problemas comuns

| Sintoma | Causa provável | Como resolver |
|---|---|---|
| A página mostra **"Não foi possível carregar a lista de eventos"** | Erro de escrita no JSON (vírgula faltando ou sobrando, aspas curvas) | Revise as [regras de ouro](#regras-de-ouro-do-json-evitam-99-dos-erros) e valide no jsonlint. |
| O evento **não aparece**, mas há um aviso amarelo no topo | Campo faltando/vazio ou **categoria escrita diferente** | Compare com o exemplo. Abra o console (F12) para ver qual evento tem o problema. |
| O evento aparece na **categoria errada** ou some | `categoria` com grafia diferente das três oficiais | Copie e cole exatamente: `UFVJM`, `Congressos e simpósios` ou `Feiras e encontros`. |
| O evento **não aparece** e há um aviso amarelo no topo | `link` sem `https://` (o site só exibe eventos com link válido) | Inicie sempre o link com `https://`. |
| A imagem não carrega | Nome do arquivo diferente (maiúsculas, extensão) | Confira o nome em `imagens/`. Enquanto isso, o site mostra uma capa verde padrão. |
| Fiz a alteração e nada mudou | O GitHub Pages leva 1–2 minutos / cache do navegador | Aguarde e recarregue com **Ctrl + F5**. |

---

## Publicar no GitHub Pages (feito uma única vez)

1. Crie um repositório **público** no GitHub (ex.: `agroprecision`) e envie todos os arquivos desta pasta para a raiz dele.
2. Vá em **Settings → Pages**.
3. Em **Build and deployment → Source**, escolha **Deploy from a branch**.
4. Em **Branch**, selecione `main` e a pasta `/ (root)`. Clique em **Save**.
5. Aguarde 1–2 minutos. O endereço será: `https://SEU_USUARIO.github.io/agroprecision/`.

---

## Personalização rápida (para quem mexe no código)

Tudo está comentado no `index.html`.

- **Texto do "Sobre"**: seção `<section id="sobre">`.
- **Contatos do rodapé** (e-mail, Instagram, GitHub): procure o comentário *"TROQUE OS ENDEREÇOS"* dentro do `<footer>`.
- **Cores**: objeto `tailwind.config` no início do arquivo (paleta `brand`).
- **Categorias** (nomes, ordem e títulos): objeto `CONFIG.categorias` no `<script>`. Se mudar um nome aqui, mude também no `eventos.json`.

### Testar no seu computador
Por segurança, navegadores não deixam o `fetch` ler arquivos abrindo o `index.html` com duplo clique. Rode um servidor local na pasta do projeto:

```bash
python -m http.server 8000
```

e abra <http://localhost:8000>.

---

## Contribuindo e licença

Contribuições são bem-vindas via *issues* e *pull requests*. Escolha uma licença open source e adicione o arquivo `LICENSE` ao repositório (sugestão: [MIT](https://choosealicense.com/licenses/mit/)).
