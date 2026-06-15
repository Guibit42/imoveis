# 🏠 Imóveis à Venda — Site de Anúncios

Site mobile-first para anunciar 3 apartamentos com QR Code, WhatsApp e agendamento de visitas.

---

## 📂 Estrutura

```
imoveis/
  index.html              ← Home com os 3 imóveis
  601.html                ← Cobertura 601 (fotos + info + outras unidades + WhatsApp)
  202.html                ← Área Privativa 202
  402.html                ← Tipo 402
  style.css               ← Estilo compartilhado (mobile-first)
  qrcodes/                ← QR Codes prontos para imprimir
```

## 🚀 Fluxo do Usuário

```
QR Code na janela → Página completa do imóvel
                      ├─ Foto principal
                      ├─ Galeria de imagens
                      ├─ Dados e diferenciais
                      ├─ Localização
                      ├─ Ver outras unidades
                      ├─ [Falar no WhatsApp]
                      └─ [Agendar Visita] → Google Agenda
```

---

## 📦 PASSO A PASSO PARA PUBLICAR

### 1️⃣ Criar conta no GitHub (se não tiver)
- Acesse https://github.com e crie uma conta gratuita

### 2️⃣ Criar repositório
- Clique em **New Repository**
- Nome: `imoveis` (ou o nome que preferir)
- Marque **Public**
- Clique **Create repository**

### 3️⃣ Subir os arquivos
No Terminal do Mac:

```bash
# Entre na pasta do projeto
cd ~/.openclaw/workspace/imoveis

# Inicie o git
git init
git add .
git commit -m "Site de imóveis"

# Conecte com seu repositório (substitua SEU-USUARIO)
git remote add origin https://github.com/SEU-USUARIO/imoveis.git
git branch -M main
git push -u origin main
```

### 4️⃣ Ativar GitHub Pages
- Vá nas **Settings** do repositório
- Menu lateral: **Pages**
- Source: **Deploy from a branch**
- Branch: **main** → `/ (root)` → Save
- Aguarde 1 minuto. Seu site estará em:
  ```
  https://SEU-USUARIO.github.io/imoveis/
  ```

### 5️⃣ Gerar QR Codes
Após o site estar no ar, gere 3 QR codes:

| Imóvel | URL do QR Code |
|--------|---------------|
| Cobertura 601 | `https://SEU-USUARIO.github.io/imoveis/601.html` |
| Área Privativa 202 | `https://SEU-USUARIO.github.io/imoveis/202.html` |
| Tipo 402 | `https://SEU-USUARIO.github.io/imoveis/402.html` |

Use https://www.qr-code-monkey.com (gratuito, alta qualidade, permite logo no centro).

---

## 📅 Configurar Agendamento (Google Agenda)

### Criar horários de visita:
1. Acesse https://calendar.google.com
2. Clique em **Criar** → **Agendamento com horários**
3. Configure:
   - Título: "Visita — Apartamento [número]"
   - Duração: 30 min
   - Dias e horários disponíveis
   - Local: endereço do imóvel
4. Salve e copie o **link da página de agendamento**
5. Substitua o `#` no atributo `href` do botão "Agendar Visita" em cada `*-detalhes.html`

Exemplo:
```html
<!-- Antes -->
<a href="#" class="btn btn-schedule">

<!-- Depois -->
<a href="https://calendar.google.com/calendar/appointments/schedules/..." class="btn btn-schedule">
```

---

## 📸 Adicionar Fotos

Substitua os placeholders `📸 Foto 1`, `📸 Foto 2` etc. por imagens reais:

**Opção A — Fotos na mesma pasta:**
1. Coloque os arquivos .jpg na pasta `imoveis/`
2. Substitua no HTML:
```html
<!-- Antes -->
<div class="gallery-item">📸 Foto 1</div>

<!-- Depois -->
<div class="gallery-item">
  <img src="cobertura-601-sala.jpg" alt="Sala da Cobertura 601">
</div>
```

**Opção B — Fotos em CDN/pasta separada (recomendado):**
Crie uma pasta `img/` e referencie como `src="img/foto.jpg"`

---

## 🔧 Personalizações Rápidas

| O que mudar | Onde |
|-------------|------|
| Telefone WhatsApp | Trocar `5531987733252` em todos os links `wa.me` |
| Preços | Alterar nos `<p class="price">` e links WhatsApp |
| Diferenciais | Editar `<ul class="features">` em cada detalhes |
| Mapa | Substituir `<div class="map">` por iframe do Google Maps |
| Cor principal | Mudar `--primary` no `style.css` |

---

## ✅ Checklist

- [ ] Criar repositório no GitHub
- [ ] Subir arquivos
- [ ] Ativar GitHub Pages
- [ ] Gerar QR Codes com URLs reais
- [ ] Imprimir placas com QR Code + telefone
- [ ] Configurar Google Agenda (Agendamento com horários)
- [ ] Atualizar links de agendamento nos HTMLs
- [ ] Adicionar fotos reais
- [ ] Testar no celular (escanear QR Code → navegar)

---

Qualquer dúvida, é só me chamar. 🏠
