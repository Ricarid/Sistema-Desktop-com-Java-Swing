# Clínica Veterinária

Sistema desktop em **Java Swing** com padrão **MVC** e banco de dados **SQLite**, para controlar tutores, animais, veterinários e consultas de uma clínica veterinária.

## Funcionalidades

- Cadastro, edição, exclusão e busca de **espécies, tutores, animais e veterinários**
- Agendamento de **consultas**, com opção de marcar como realizada ou cancelar
- Painel inicial com indicadores e próximas consultas
- Validações (CPF, datas, valores) e regras de negócio (ex.: não excluir tutor que possui animais)

## Tecnologias

- Java 21
- Maven
- Swing + FlatLaf (visual)
- SQLite (via JDBC)

## Como executar

1. Instale o **JDK 21** e o **Maven**.
2. Na pasta do projeto, rode:

   ```
   mvn compile exec:java
   ```

   Ou abra o projeto na IDE e execute a classe `br.edu.univille.poo.clinica.App`.

O arquivo de banco `clinica.db` é criado automaticamente na primeira execução, já com dados de exemplo. Para recomeçar do zero, feche o sistema e apague esse arquivo.

## Estrutura (MVC)

```
model/    entity (dados), dao (SQL), usecase (regras), exception, database
control/  controllers (ligam as telas às regras)
view/     telas Swing
util/     CPF, datas e valores
```

Fluxo: **View → Controller → UseCase → DAO → Banco**

## Banco de dados

Tabelas: `especie`, `tutor`, `animal`, `veterinario` e `consulta` (script em `script.sql`).

| Diagrama de classes | MER |
|---|---|
| ![Classes](docs/diagrama-de-classes.png) | ![MER](docs/mer.png) |
