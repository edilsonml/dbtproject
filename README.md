Projeto Database Northwind
Curso DBT Prof.Fernando Amaral

### Etapas do projeto:
1. Criação de cluster redshift
2. Criação de database Northwind
3. Criação do schema e das tabelas: order_details, order, customers, employees, suppliers, products, products categories e shippers.
4. Realizar a carga das tabelas copiando os dados do S3.
5. Criação de projeto DBT
6. Criação dos modelos para realização dos seguintes tratamentos:

- Remover o clientes Duplicados:
  - company_name
  - contact_name

- Criar colunas calculadas: 
  - Age (birth_date)
  - LengthofService (hire_date)
  - Name (last_name + first_name)

- Criar colunas calculadas: 
  - Total (unit price * quantity)
  - Discount (Total - (product.unitprice * quantity)
 
- Criar tabela desnormalizada para grupo de BIs users:

    1. Left-Join 
      Product- Supplier
      Products – Categories      
    2. Left-Join OrderDetais – Modelo 1
    3. Left-Join 
      Orders – Customers
      Orders – Employees
      Orders – Shippers
    4. Inner-Join 
      Modelo 2 – Modelo 3

7. Particionar tabela de orders por ano (2020, 2021, 2022)

### Saida do projeto

![image](https://user-images.githubusercontent.com/68425961/198371794-24b76a4e-792d-451c-a789-7aea1d659355.png)


### Resources:
- Dbt Cloud
- Amazon Redshift
- Amazon S3.
