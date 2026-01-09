# Módulo: Website Live Chat

## Información General
- **Nombre técnico:** website_livechat
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** website, im_livechat


## Propósito
Chat with your website visitors



## Descripción

Allow website visitors to chat with the collaborators. This module also brings a feedback tool for the livechat and web pages to display your channel with its ratings on the website.
    



## Modelos

### website


- Hereda de:

  - website




- Campos:

  - **channel_id** (Many2one) → im_livechat.channel





### chatbot.script


- Hereda de:

  - chatbot.script




- No agrega campos



### im_livechat.channel


- Hereda de:

  - im_livechat.channel




- No agrega campos



### im_livechat.channel


- Hereda de:


  - im_livechat.channel

  - website.published.mixin





- Campos:

  - **website_description** (Html) → Website description





### discuss.channel


- Hereda de:

  - discuss.channel




- Campos:

  - **livechat_visitor_id** (Many2one) → website.visitor





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **channel_id** (Many2one) → im_livechat.channel





### chatbot.script.step


- Hereda de:

  - chatbot.script.step




- No agrega campos



### ir.http


- Hereda de:

  - ir.http




- No agrega campos



### website.visitor


- Hereda de:

  - website.visitor




- Campos:

  - **livechat_operator_id** (Many2one) → res.partner


  - **livechat_operator_name** (Char) → Operator Name


  - **discuss_channel_ids** (One2many) → discuss.channel


  - **session_count** (Integer) → # Sessions








## Vistas


### im_livechat.channel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | im_livechat.channel.view.form.add | `website_livechat.im_livechat_channel_view_form_add` | - |


