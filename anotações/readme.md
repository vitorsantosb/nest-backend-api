### Anotações
    Comando de criação de modulos: nest g module "module-name"

Aplicações nest tem o modulo principal(raiz) que inicializa a aplicação. 

Um modulo possui
```ts
@Module({
  imports: [], //Lista de módulos necessários para este módulo.
  controllers: [], // Array de controllers que devem ser instancias dentro de um módulo.
  providers: [], //Array de providers que devem está disponiveis dentro do módulo via injeção de dependencias
  exports: [], // Array de providers que devem ser exportados para outros módulos.
})
```

## Controllers: 
#### Responsável por lidar com as requisições HTTPS

- Handlers: São métodos implementados dentro da classe controller que são anotados com os decorators @GET, @POST, @DELETE, @PUT
- Podem utilizar injeção de dependência para consumir providers.

```ts
import { Controller } from "@nestjs/common";

@Controller('api/v1/jogadores') // a string dentro do decorator é a rota o qual é utilizado para acessar a controller.
export class JogadoresController {};
```

Caso queira definir um HTTP Status code no escopo basta adicionar uma nova variável basta adicionar um novo decorator seguindo o exemplo abaixo

```ts
import { Controller } from "@nestjs/common";

@Controller('api/v1/jogadores') // a string dentro do decorator é a rota o qual é utilizado para acessar a controller.
@Post()
@HttpCode(204) //Status code o qual a rota jogadores/post retornara ao usuário.
create() {
  return 'This action adds a new cat';
}
```

Caso não utilize o decorator  ```HttpCode()``` por padrão o nest ira retorna os valores padrões da propria api do nest como 201 - para Create e 200 para sucesso!


### Decorators para funções express;
```

@Request(), @Req()	    req
@Response(), @Res()*	    res
@Next()	                    next
@Session()	            req.session
@Param(key?: string)	    req.params / req.params[key]
@Body(key?: string)	    req.body / req.body[key]
@Query(key?: string)	    req.query / req.query[key]
@Headers(name?: string)	    req.headers / req.headers[name]
@Ip()	                    req.ip
@HostParam()	            req.hosts

```

### Controllers status code

- https://docs.nestjs.com/controllers#status-code


### Providers

- Providers podem ser injetados dentro de construtores, se decorado com a anotação ```@Injectable```, via injeção de dependência
- Podem ser classe sync/async e factory's e etc
- Providers devem ser fornecidos por um módulo para que se tornem utilizáveis.
- Podem ser exportados por um módulo, se tornando disponíveis para um outro módulo importa-los.

### Services 

- São definidos como providers, porém, nem todos providers são services;
- Tratam-se de um conceito comum no contexto de desenvolvimento de software
e não são exclusivos do NestJS, JavaScript ou qualquer tecnologia de
desenvolvimento backend;
- São singletons, quando decorados com ```@Injectable()```, e fornecidos a um module.
Ou seja, uma mesma instância será compartilhada em toda a aplicação;
- É onde nossa lógica de negócios deverá ser implementada.

