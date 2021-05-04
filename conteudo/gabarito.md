# Gabarito dos exercícios
## Parte - I
### Exercício 1.1

```
.answers {
  display: flex;
  justify-content: flex-end;
}
```

### Exercício 1.2

```
.answers {
  display: flex;
  flex-direction: row-reverse;
  justify-content: center; 
}
```

### Exercício 1.3

```
.answers {
  display: flex;
  flex-direction: column;
}
```

### Exercício 1.4

```
.answers {
  display: flex;
  flex-direction: column-reverse;
  justify-content: space-between;
  align-items: center;
}
```

### Exercício 1.5

```
.answers {
  display: flex;
  justify-content: space-around;
  align-items: flex-end;
}
```

### Exercício 1.6

```
.answers {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
```

## Parte - II
### Exercício 2.1

```
.answers {
  flex-wrap: wrap;
  align-content: space-around;
}
```

### Exercício 2.2

```
.answers {
  flex-wrap: wrap-reverse;
  align-content: flex-start;
}
```

### Exercício 2.3

```
.answers {
  flex-direction: column;
  flex-wrap: wrap;
  align-content: space-between; 
}
```

### Exercício 2.4

```
.answers {
  flex-direction: row-reverse;
  flex-wrap: wrap;
  align-content: center; 
}
```

### Exercício 2.5

```
.answers {
  flex-wrap: wrap;
  align-content: space-evenly; 
}
```
## Bônus

Para consertar o Clone do Course você deverá aplicar as seguintes propriedades:

```
.course-page , .header , .left-header , .right-header{
  display: flex;
}

.course-page {
  flex-direction: column;
} 

.header {
  justify-content: space-between;
}

.left-header , .right-header {
  align-items: center;
}

.hard-skill-cards {
  display: flex;
  flex-direction: column;
}

.section {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
}

.section-2-card {
  display: flex;
}

.section-2-card div {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

footer {
  display: flex;
  justify-content: space-between;
}
```
