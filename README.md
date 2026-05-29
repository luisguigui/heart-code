# 💓 Heart Code - Animated Heart

Uma página web interativa e emocionante com uma animação 3D de coração pulsante, partículas flutuantes e mensagens de amor que aparecem em forma de coração. Combinação perfeita de CSS 3D, animações suaves e design moderno.

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)

---

## ✨ Características Principais

### 💖 Coração Animado 3D
- **Coração pulsante** com efeito de respiração suave
- **Gradientes radiais** que criam profundidade e brilho
- **Rotação 3D** com perspectiva realista
- **Drop shadow glow** para efeito luminoso

### 🌟 Partículas Flutuantes
- **28 partículas animadas** flutuando continuamente
- **Efeito de brilho** com gradientes radiais
- **Movimento orgânico** com desvio lateral aleatório
- **Opacidade variável** para profundidade natural

### 💬 Mensagens Dinâmicas
- **260 textos "I love you"** dispostos em forma de coração
- **Animação 3D** com rotação e desaparecimento gradual
- **Efeito de fade-in/fade-out** sincronizado
- **Distribuição matemática** em padrão cardíaco

### 🎨 Design Luxuoso
- **Paleta de cores neon** em tons de rosa (#ff4d6d, #ff758f)
- **Fundo degradado** com camadas de profundidade
- **Texto com glow effect** luminoso
- **Espaçamento tipográfico** profissional

### 📱 Totalmente Responsivo
- Adapta-se perfeitamente a qualquer tamanho de tela
- Usa `clamp()` para escalabilidade proporcional
- Otimizado para mobile, tablet e desktop

---

## 🚀 Como Usar

### 1. Abrir Diretamente
Simplesmente abra o arquivo `heart.html` em seu navegador:

```bash
# Windows
start heart.html

# macOS
open heart.html

# Linux
xdg-open heart.html
```

### 2. Usando um Servidor Local
Para melhor desempenho, sirva através de HTTP:

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js
npx http-server
```

Acesse `http://localhost:8000/heart.html`

### 3. Incorporar em Seu Site
```html
<iframe src="heart.html" width="100%" height="100vh" frameborder="0"></iframe>
```

---

## 🎨 Estrutura Visual

### Camadas 3D
```
┌─────────────────────────────┐
│  Textos Flutuantes (z:220)  │
├─────────────────────────────┤
│  Centro de Mensagem (z:120) │
├─────────────────────────────┤
│  Núcleo do Coração (z:70)   │
├─────────────────────────────┤
│  Borda do Coração (z:20)    │
├─────────────────────────────┤
│  Partículas de Fundo (z:0)  │
└─────────────────────────────┘
```

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Propósito |
|-----------|----------|
| **HTML5** | Estrutura semântica |
| **CSS3** | Animações 3D e estilos |
| **JavaScript** | Lógica de renderização dinâmica |
| **Tailwind CSS** | Utilitários CSS |
| **CSS Custom Properties** | Variáveis de cor e estilo |

---

## 🎬 Animações

### Heart Pulse (5.8s)
Pulsação do coração com escala e rotação:

```css
@keyframes heart-pulse {
  0%   { scale: 1;    rotate: 10deg; }
  18%  { scale: 1.08; rotate: 8deg;  }
  36%  { scale: 1.16; rotate: -7deg; }
  54%  { scale: 1.06; rotate: 5deg;  }
  72%  { scale: 1.2;  rotate: -4deg; }
  100% { scale: 1;    rotate: 10deg; }
}
```

### Core Breath (5.8s)
Respiração do núcleo do coração:

```css
@keyframes core-breath {
  0%, 100% { scale: 0.92; opacity: 0.78; }
  50%      { scale: 1.06; opacity: 1;    }
}
```

### Text Fade In (4.8s)
Textos aparecem, rotacionam e desaparecem:

```css
@keyframes text-fade-in {
  0%   { opacity: 0; transform: translate3d(...) rotateY(var(--ry)) scale(0.8); }
  18%  { opacity: 0.92; }
  50%  { opacity: 1; transform: translate3d(...) rotateY(calc(var(--ry) + 10deg)); }
  82%  { opacity: 0.88; }
  100% { opacity: 0; transform: translate3d(...) rotateY(calc(var(--ry) + 25deg)); }
}
```

### Title Glow (2.8s)
Título com efeito de brilho pulsante:

```css
@keyframes title-glow {
  0%, 100% { text-shadow: 0 0 8px rgba(...), 0 0 22px rgba(...); }
  50%      { text-shadow: 0 0 12px rgba(...), 0 0 30px rgba(...); }
}
```

### Float Up (8-18s)
Partículas flutuam para cima com desvio:

```css
@keyframes floatUp {
  0%   { translate: 0 110vh scale(0.7);        opacity: 0;   }
  10%  {                                        opacity: 0.8; }
  100% { translate: var(--drift) -20vh scale(1.25); opacity: 0; }
}
```

---

## 📐 Matemática do Coração

### Equação Paramétrica
A posição de cada texto é calculada usando a famosa equação do coração:

```javascript
function getHeartPosition(t) {
  const x = 16 * Math.pow(Math.sin(t), 3);
  const y = -(13 * Math.cos(t) - 5 * Math.cos(2*t) - 2 * Math.cos(3*t) - Math.cos(4*t));
  return { x, y };
}
```

Onde `t` varia de 0 a 2π, criando uma forma perfeita de coração.

### Geração de Textos
260 textos são distribuídos ao longo da curva do coração:

```javascript
for (let i = 0; i < totalTexts; i++) {
  const t = (i / totalTexts) * Math.PI * 2;  // Distribuição uniforme
  const pos = getHeartPosition(t);             // Posição na curva
  // Aplicar escala e variação aleatória
}
```

---

## 🎨 Customização

### Alterar Mensagem Principal
Procure por esta linha no HTML:

```html
<h1>I LOVE YOU</h1>
<p>para alguem que me ama</p>
```

### Mudar Cores
As cores estão no `:root` do CSS:

```css
:root {
  --bg: #050505;           /* Fundo */
  --pink: #ff4d6d;         /* Rosa primário */
  --pink2: #ff758f;        /* Rosa secundário */
  --glow: 0 0 8px rgba(...) /* Efeito de brilho */
}
```

Exemplos de paletas:
- **Vermelho**: `--pink: #ff0000; --pink2: #ff6b6b`
- **Roxo**: `--pink: #c520f0; --pink2: #d946ef`
- **Azul**: `--pink: #0099ff; --pink2: #00ccff`

### Alterar Texto Flutuante
Procure por esta linha no JavaScript:

```javascript
span.innerText = 'I love you';  // Mude o texto
```

### Mudar Quantidade de Partículas
```javascript
for (let i = 0; i < 28; i++) {  // Altere 28 para quantidade desejada
```

### Ajustar Velocidade das Animações
Procure por estas durações:

```javascript
// Em keyframes CSS:
animation: heart-pulse 5.8s infinite ease-in-out;  // Tempo do coração
animation: core-breath 5.8s infinite ease-in-out;  // Tempo do núcleo
animation: text-fade-in 4.8s infinite ease-in-out; // Tempo dos textos
```

---

## 📊 Performance

| Métrica | Valor |
|---------|-------|
| Textos renderizados | 260 |
| Partículas | 28 |
| Tamanho do arquivo | ~8.7 KB |
| Dependências externas | 1 (Tailwind CDN) |
| FPS alvo | 60 |

### Otimizações Aplicadas
✅ Uso de `will-change` para melhor performance  
✅ `transform` ao invés de posição absoluta  
✅ CSS animations (GPU accelerated)  
✅ `filter` com blur otimizado  
✅ Drop shadows em vez de box-shadows (mais rápido)  

---

## 🌐 Compatibilidade

| Navegador | Status | Notas |
|-----------|--------|-------|
| **Chrome** | ✅ | Suporte completo |
| **Firefox** | ✅ | Suporte completo |
| **Safari** | ✅ | iOS 12+ |
| **Edge** | ✅ | Baseado em Chromium |
| **Opera** | ✅ | Suporte completo |
| **IE 11** | ❌ | Não suportado (CSS 3D) |

### Recursos Necessários
- ✅ CSS 3D Transforms
- ✅ CSS Animations
- ✅ CSS Gradients
- ✅ ES6 JavaScript
- ✅ Flexbox

---

## 📱 Responsividade

Totalmente adaptável para todos os dispositivos:

```
┌─────────────────┐  ┌──────────────┐  ┌──────────────────┐
│ Mobile (360px)  │  │ Tablet (768) │  │ Desktop (1920)   │
│                 │  │              │  │                  │
│    Heart 96vw   │  │ Heart 82vw   │  │  Heart 760px     │
│                 │  │              │  │                  │
└─────────────────┘  └──────────────┘  └──────────────────┘
      ✅              ✅                  ✅
```

---

## 🔧 Troubleshooting

### "Coração não anima"
- Verifique se o JavaScript está habilitado
- Limpe o cache do navegador (Ctrl+F5)
- Teste em outro navegador moderno

### "Textos não aparecem"
- Verifique console para erros (F12)
- Certifique-se de que o Tailwind CSS carregou
- Aumente zoom se os textos forem muito pequenos

### "Performance lenta"
- Reduza o número de partículas
- Desabilite outras abas/extensões
- Use versão recente do navegador
- Ative aceleração de GPU nas configurações

### "Animação travando"
- Diminua a quantidade de efeitos simultâneos
- Verifique uso de CPU/GPU
- Recarregue a página
- Tente modo de leitura se disponível

---

## 💡 Casos de Uso

- 💌 Cartão eletrônico de amor
- 💍 Proposta criativa
- 🎁 Aniversário ou data especial
- 💝 Mensagem romântica
- 🎨 Portfolio criativo
- 🌹 Página de relacionamento
- 📧 Email marketing criativo
- 🎬 Landing page
- 🎵 Videoclip ou conteúdo multimedia

---

## 🎓 Aprendizados

Este projeto demonstra:

✅ CSS 3D Transforms  
✅ Animations e Keyframes  
✅ JavaScript para geração dinâmica de DOM  
✅ Matemática em programação (equação do coração)  
✅ Design responsivo com clamp()  
✅ Otimização de performance  
✅ Efeitos visuais modernos  
✅ Tipografia com glow effects  

---

## 📝 Licença

Este projeto está licenciado sob a Licença MIT - sinta-se livre para usar, modificar e compartilhar!

---

## 👨‍💻 Autor

**Luis Guigui**
- GitHub: [@luisguigui](https://github.com/luisguigui)
- Repositório: [heart-code](https://github.com/luisguigui/heart-code)

---

## 🌟 Agradecimentos

- Comunidade web criativa
- Inspiração em design moderno
- Tailwind CSS por ferramentas excelentes
- Stack Overflow e MDN Web Docs

---

## 🔗 Recursos Relacionados

- [MDN: CSS 3D Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate3d)
- [MDN: CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [Equação Matemática do Coração](https://en.wikipedia.org/wiki/Heart_curve)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)

---

## 💬 Feedback

Adorou? Deixe uma ⭐ no GitHub!

Encontrou um problema? Abra uma [Issue](https://github.com/luisguigui/heart-code/issues)

Tem uma sugestão? Crie um [Discussion](https://github.com/luisguigui/heart-code/discussions)

---

**Desenvolvido com ❤️ em HTML/CSS/JavaScript**

*"O código é poesia, e o design é emoção."*

### 🎬 Experimente Agora
Abra `heart.html` no seu navegador e deixe seu coração cantar! ✨
