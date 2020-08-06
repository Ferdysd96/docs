## SEQUELIZE


## COMANDOS

```bash
# Instalar CLI
$ npm install --save sequelize-cli

# Inicializar
$ npx sequelize-cli init

# Crear modelo y migracion
$ npx sequelize-cli model:generate --name User --attributes firstName:string,lastName:string,email:string

# Solo generar migracion
$ npx sequelize-cli migration:generate --name nombre

# Generar Seeder 
$ npx sequelize-cli seed:generate --name nombre

# Migaracion
$ npx sequelize-cli db:migrate
```
