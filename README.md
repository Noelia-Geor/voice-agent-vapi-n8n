# 🎙️ Agente de Voz con VAPI + n8n

Agente de voz para automatización de llamadas entrantes construido con **VAPI**, **n8n** y **OpenAI**.  
Diseñado para atender llamadas de clientes de forma autónoma 24/7, captar información y derivar al equipo cuando es necesario.

> ⚡ En producción real como servicio de GeorLabs desde 2025.

---

## 🎯 ¿Qué hace este agente?

- Atiende llamadas entrantes de forma autónoma
- Identifica la intención del cliente en los primeros 30 segundos
- Recoge datos clave: nombre, negocio, sector, motivo de llamada
- Agenda citas directamente o transfiere al equipo humano
- Envía resumen de la llamada por WhatsApp al comercial vía n8n
- Maneja silencios, interrupciones y cambios de tema de forma natural

---

## 🏗️ Arquitectura

```
Llamada entrante (cliente)
        │
        ▼
      VAPI
  (orquestador de voz)
        │
   ┌────┴────┐
   │         │
OpenAI    Webhook
(LLM)     → n8n
   │         │
   └────┬────┘
        │
   ┌────▼─────────────┐
   │ n8n workflows    │
   │ - Guardar lead   │
   │ - Avisar equipo  │
   │ - Agendar cita   │
   └──────────────────┘
```

---

## 🛠️ Stack tecnológico

| Componente | Tecnología |
|---|---|
| Orquestador de voz | VAPI |
| LLM | OpenAI GPT-4o |
| Automatización | n8n (self-hosted) |
| Notificaciones | WhatsApp vía Evolution API |
| Base de datos | Google Sheets |

---

## ⚙️ Requisitos

- Cuenta VAPI (plan gratuito suficiente para empezar)
- OpenAI API Key
- n8n self-hosted
- Evolution API (para notificaciones WhatsApp)
- Número de teléfono en VAPI (USA gratuito o España de pago)

---

## 💡 Diferencias clave vs agente de texto

| Aspecto | WhatsApp | Voz |
|---|---|---|
| Frases | Pueden ser largas | Máximo 2 oraciones |
| Confirmaciones | Opcionales | Frecuentes y explícitas |
| Silencios | No existen | Hay que gestionarlos |
| Interrupciones | No existen | El agente debe ceder |
| Emojis | Sí | No |

---

## 📋 Próximamente

- [ ] Workflow n8n completo de integración
- [ ] System prompt documentado para agente de voz
- [ ] Guía de configuración paso a paso en VAPI
- [ ] Ejemplo de transferencia a humano

---

## 👤 Autora

**Noelia Soto** — AI Automation Specialist & Technical Founder  
[LinkedIn](https://linkedin.com/in/noeliasotovega) · [GeorLabs](https://georlabs.com) · [Email](mailto:sotoveganoelia@gmail.com)

---

## 📄 Licencia

MIT License — libre para usar, modificar y distribuir con atribución.
