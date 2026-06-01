# 📅 Agenda Diária

<p align="center">
  Workflow N8N que consulta o Google Calendar diariamente e envia um resumo dos eventos do dia via WhatsApp.
</p>

---

## 📌 Visão Geral

Este workflow automatiza o envio diário da agenda pessoal via WhatsApp. Em um horário fixo configurado, ele consulta o Google Calendar, verifica se há eventos no dia e envia uma mensagem formatada. Caso não haja eventos, também notifica.

---

## ⚙️ Como funciona

```
Schedule Trigger → Google Calendar → Verifica eventos → Formata mensagem → WhatsApp (Evolution API)
```

1. Dispara automaticamente no horário configurado
2. Busca todos os eventos do dia no Google Calendar
3. Se houver eventos → envia lista formatada via WhatsApp
4. Se não houver eventos → envia mensagem informando

---

## 📊 Resultado

🖼️ Exemplo de mensagem recebida no WhatsApp:

![Agenda Diária](images/example.png)

---

## 🛠️ Stack

- [N8N](https://n8n.io/) — orquestração do workflow
- [Google Calendar API](https://developers.google.com/calendar) — consulta de eventos
- [Evolution API](https://evolution-api.com/) — envio de mensagens via WhatsApp

---

## 🚀 Como usar

Clone ou baixe o repositório e importe o workflow no N8N:

    Settings → Workflows → Import from file → agenda-diaria.json

Após importar, configure:

1. **Credencial do Google Calendar** — OAuth2 no N8N
2. **Nós HTTP Request** — substitua `YOUR_EVOLUTION_API_KEY` pela sua API key da Evolution API
3. **Nó Code** e **HTTP Request** — substitua `YOUR_WHATSAPP_NUMBER` pelo seu número no formato `5511999999999`
4. **Nó Calendário** — substitua `YOUR_GOOGLE_CALENDAR_EMAIL` pelo seu e-mail do Google Calendar
5. **Schedule Trigger** — ajuste o horário de disparo conforme preferir
6. Ative o workflow

---

## 📌 Observações

- O workflow remove eventos duplicados no mesmo horário antes de formatar a mensagem
- A mensagem é enviada mesmo quando não há eventos no dia
- O horário padrão configurado é **06:30** (America/Sao_Paulo)
