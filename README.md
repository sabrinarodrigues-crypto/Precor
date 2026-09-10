<div align="center">

# 🛡️ PRECOR
### Prevenção, Comunicação e Resposta a Situações de Risco

**Aplicativo complementar de segurança para ambientes industriais**

*Projeto Integrador I*

### 🔗 [Acessar o protótipo online](https://sabrinarodrigues-crypto.github.io/Precor/)

</div>

---

## 📋 Sobre o projeto

O **PRECOR** é um protótipo funcional de aplicativo web voltado à **segurança do trabalho em ambientes industriais**. Ele não substitui alarmes, procedimentos ou sistemas de segurança já existentes em uma unidade — sua proposta é atuar como uma **segunda camada de comunicação**, reduzindo a dependência de um único canal para que informações críticas de risco cheguem rapidamente às pessoas e setores certos.

O projeto foi desenvolvido a partir da análise de um ambiente industrial real, tendo como referência a **Unidade de Sarapuí**, da **Universal Chemical** — empresa especializada na industrialização de saneantes/domissanitários, cosméticos e produtos de higiene pessoal e para a saúde.

A solução se estrutura em **três pilares**:

| Pilar | O que faz |
|---|---|
| 🔎 **Prevenção** | Identificação antecipada de riscos por colaboradores e, experimentalmente, por monitoramento de sensores com predição de tendência |
| 📢 **Comunicação** | Alertas direcionados por área, função e criticidade, com confirmação de recebimento |
| 🚑 **Resposta** | Acompanhamento da ocorrência até o encerramento, com procedimentos de segurança sugeridos automaticamente |

---

## 🎓 Contexto acadêmico

- **Disciplina:** Projeto Integrador I
- **Professora orientadora:** Silvia Garcia
- **Integrantes:** Sabrina Fogaça, Ticiane Garcia e Pablo Henrique
- **Empresa de referência:** Universal Chemical — Unidade de Sarapuí (SP)
- **Área de aplicação:** Segurança do Trabalho

### Problema identificado

A partir da observação do ambiente industrial, foram identificadas oportunidades de melhoria relacionadas à **prevenção** e à **comunicação de situações de risco**: dependência de um único canal de comunicação de emergência, dificuldade de disseminar rapidamente informações críticas entre áreas diferentes, e a necessidade de reconhecer condições anormais antes que evoluam para ocorrências mais graves.

---

## 👥 Perfis de usuário

O sistema possui **5 perfis** com permissões e visões distintas, cada uma escopada por área ou função:

| Perfil | O que pode fazer |
|---|---|
| **Liderança** | Registra ocorrências, acompanha ocorrências e sensores da própria área |
| **Brigadista** | Recebe alertas de emergência, marca ocorrências como resolvidas com relato do que foi feito, recebe sugestões de procedimentos da biblioteca |
| **Segurança do Trabalho** | Visão geral da unidade, gestão de ocorrências, indicadores, duplo-check de encerramento, cadastro de procedimentos |
| **Setor Responsável** | Vê apenas ocorrências e sensores direcionados à sua função (ex.: Manutenção Elétrica) |
| **Administrador / TI** | Gestão de usuários, registro de logs e logins, configuração da unidade, visão total do sistema |

---

## ✨ Funcionalidades principais

**Ocorrências e emergências**
- Registro completo de ocorrência (tipo, local, criticidade, setor responsável)
- Fluxo rápido de emergência (2 toques, para situações críticas sem tempo a perder)
- Linha do tempo de status: Registrada → Encaminhada → Em atendimento → Resolvida → Encerrada
- Duplo-check de encerramento pela Segurança do Trabalho
- Anexo de imagem como comprovação em qualquer atualização de status

**Alertas**
- Central de alertas com confirmação de recebimento e ação direta ("Confirmar e atender ocorrência")
- Notificação sonora e visual (toast) para alertas críticos, mesmo em outra tela

**Monitoramento preventivo (dados simulados)**
- Sensores por área/setor com limites de Normal / Atenção / Anormal / Crítico
- **Predição de tendência**: o sistema estima se um sensor está piorando e gera alerta preventivo antes mesmo de cruzar o limite
- Mini-gráfico (sparkline) do histórico recente de cada sensor
- Registro manual de leituras de campo

**Biblioteca de Segurança**
- Procedimentos por categoria (incêndio, vazamento, evacuação etc.)
- Sugestão automática do procedimento correspondente ao tipo de ocorrência, exibida direto para o Brigadista

**Gestão e indicadores**
- Painel de indicadores (ocorrências por criticidade, área e tipo, taxa de encerramento)
- Exportação de relatório em PDF (por ocorrência) e CSV (lista filtrada)
- Busca global (ocorrências, procedimentos e alertas)
- Registro de logs de alterações e de logins (Administrador)

**Extras**
- Troca de perfil sem logout (para demonstração)
- Onboarding rápido na primeira vez que cada perfil acessa
- Instalável como aplicativo (PWA) a partir do navegador

---

## 🛠️ Tecnologias utilizadas

- **HTML5, CSS3 e JavaScript puro** — sem frameworks ou bibliotecas externas
- Arquivo único, sem necessidade de instalação, servidor ou build
- Web Audio API (alerta sonoro), Web App Manifest (instalação como PWA)

> Escolha proposital: manter o protótipo 100% autocontido em um único arquivo `.html`, facilitando a avaliação, o compartilhamento e a execução sem qualquer configuração de ambiente.

---

> 💡 O link acima usa GitHub Pages e abre direto no navegador (celular ou computador), sem precisar baixar nada. *(Se ainda não estiver ativo, confira em Settings → Pages do repositório se a publicação já foi concluída — pode levar 1-2 minutos após a configuração.)*

## ▶️ Como executar localmente (alternativa)

1. Baixe o arquivo `precor.html`
2. Abra-o com um navegador (Chrome, Safari, Edge) — em celular, use "Abrir com" e escolha o navegador, não o visualizador de arquivos padrão
3. Pronto — não precisa de servidor, instalação ou internet (exceto para carregar as fontes do Google Fonts)

### Usuários de demonstração

Na tela de login, clique em **"Ver usuários de demonstração"** e escolha qualquer perfil — a senha é preenchida automaticamente:

| Nome | Perfil | Área |
|---|---|---|
| Marcos Andrade | Liderança | Produção — Reatores |
| Fernanda Diniz | Brigadista | Brigada de Emergência |
| Carlos Bittencourt | Segurança do Trabalho | Segurança do Trabalho |
| Renata Souza | Setor Responsável | Manutenção Elétrica |
| Igor Prado | Administrador / TI | TI Industrial |

---

## ⚠️ Limitações do protótipo

- Todos os dados ficam **em memória do navegador** — são perdidos ao atualizar a página (não há backend/banco de dados)
- Sensores, leituras e ocorrências de exemplo são **dados simulados**, criados para fins de demonstração
- A predição de tendência usa um cálculo estatístico simples (regressão linear sobre as últimas leituras), com fins didáticos
- A instalação como PWA oferece o atalho na tela inicial, mas **não** funciona totalmente offline (exigiria um servidor real)

---

## 📁 Estrutura do projeto

```
precor.html      → aplicação completa (estrutura, estilo e lógica em um único arquivo)
README.md        → este arquivo
```

---

<div align="center">

**PRECOR** — uma ferramenta complementar de segurança industrial.
*Não substitui alarmes, procedimentos ou sistemas de segurança já implantados na unidade.*

</div>
