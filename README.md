# 🎯 CSS `position` - Dominando o Espaço!  

O `position` no CSS define **como um elemento é posicionado na página**. Se você já tentou alinhar algo e nada ficava onde deveria, essa propriedade vai salvar sua vida! 🤯  

## 📌 Tipos de `position`  

### 🏠 `static` (Padrão)  
Se você não define um `position`, o CSS assume que ele é `static`. Isso significa que ele **segue o fluxo normal do HTML** e não aceita `top`, `left`, `right` ou `bottom`.  

```css
.elemento {
  position: static;
}
```

---

### 📍 `relative` (Relativo a ele mesmo)

O elemento **mantém seu espaço no layout**, mas você pode mover ele com `top`, `left`, `right` e `bottom`.

```css
.elemento {
  position: relative;
  top: 20px;
  left: 30px;
}
```

---

### 🚀 `absolute` (Sai do fluxo normal)

O elemento **não ocupa mais espaço no layout** e fica posicionado **em relação ao primeiro ancestral com `position: relative`** (ou ao `<body>` se não houver um ancestral posicionado).

```css
.container {
  position: relative;
}

.elemento {
  position: absolute;
  top: 50px;
  left: 100px;
}
```

---

### 📌 `fixed` (Fixa na tela)

O elemento **não se move ao rolar a página**, ficando preso à viewport.

```css
.elemento {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

---

### 🧲 `sticky` (Gruda quando necessário)

O elemento **age como `relative` até que um certo ponto seja alcançado, então ele se fixa (`fixed`)**.

```css
.elemento {
  position: sticky;
  top: 0px;
}
```

---

### 🎚️ `z-index` (Controle da sobreposição)

```css
.elemento1 {
  position: absolute;
  top: 0;
  left: 0;
  background: lightblue;
  z-index: 1;
}

.elemento2 {
  position: absolute;
  top: 20px;
  left: 20px;
  background: tomato;
  z-index: 2;
}
```

---

## 🎨 Exemplo Prático

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Exemplo de Position</title>
  <style>
    .container {
      position: relative;
      width: 300px;
      height: 300px;
      background: lightgray;
    }

    .absolute {
      position: absolute;
      top: 50px;
      left: 50px;
      background: tomato;
      padding: 10px;
    }

    .fixed {
      position: fixed;
      bottom: 10px;
      right: 10px;
      background: gold;
      padding: 10px;
    }

    .sticky {
      position: sticky;
      top: 0;
      background: lightblue;
      padding: 10px;
    }
  </style>
</head>
<body>

  <div class="sticky">Eu sou sticky! 👀</div>
  
  <div class="container">
    <div class="absolute">Eu sou absolute! 🎯</div>
  </div>

  <div class="fixed">Eu sou fixed! 📌</div>

  <p style="height: 1000px;">Role a página para ver o efeito dos elementos! ⬇️</p>

</body>
</html>
```

---

## 📚 Resumo

| Tipo       | O que faz?                                                 | Respeita fluxo? | Exemplo de uso                       |
| ---------- | ---------------------------------------------------------- | --------------- | ------------------------------------ |
| `static`   | Posição padrão                                             | ✅ Sim           | Qualquer elemento sem `position`     |
| `relative` | Move em relação à própria posição                          | ✅ Sim           | Pequenos ajustes                     |
| `absolute` | Sai do fluxo e se move em relação ao ancestral posicionado | ❌ Não           | Tooltips, pop-ups                    |
| `fixed`    | Fica preso na tela                                         | ❌ Não           | Menus fixos                          |
| `sticky`   | Fica normal, mas gruda quando atinge um ponto              | ✅ Sim           | Cabeçalhos fixos                     |
| `z-index`  | Controla a sobreposição de elementos                       | —               | Janela modal, banners, sobreposições |

```
```
