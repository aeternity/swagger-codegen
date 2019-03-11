# Swagger Code Gen

## Prerequisities 
To build from source, you need the following installed and available in your $PATH:

* [Java 7 or 8](http://java.oracle.com)

* [Apache maven 3.3.3 or greater](http://maven.apache.org/)

## Running script
0. Clone the project: 
```
  git clone https://github.com/DanielaIvanova/swagger-codegen/ &&
  cd swagger-codegen/ &&
  git checkout elixir-adjustment
```
1. `mvn package` - to compile and build Java project.
2. To generate an `elixir` api client, by providing a `swagger.yaml` file, execute the following command:
```
  java -jar /modules/swagger-codegen-cli/target/swagger-codegen-cli.jar generate -i "PATH_TO_SWAGGER.yaml" -l elixir -o "DESTINATION_PATH"
```
3. Add `.formatter.exs` to newly generated elixir folder:
``` 
  [inputs: ["{mix,.formatter}.exs", "{config,lib,test}/**/*.{ex,exs}"]]
```
4. Run `mix deps.get && mix format && iex -S mix ` 
