# resty-typeorm

### Example

```typescript
import resty, { Controller, Get } from "@restyjs/core";
import { Database } from "@restyjs/typeorm";

@Controller("/")
class HelloController {
  @Get("/", [])
  index() {
    return "Hello World";
  }
}

const app = resty({
  controllers: [HelloController],
  providers: [
    Database({
      type: "sqlite",
      database: "example.db",
      entities: [],
    }),
  ],
});

app.listen(8080);
```
