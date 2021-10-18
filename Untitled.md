```
'{"html": "<h2>Hello WORLD</h2>","format": "png","maxKB": "500","s_id": "1234"}'
```

```bash
node -e \"console.log(require('./index').handler('{"html": "<h2>Hello WORLD</h2>","format": "png","maxKB": "500","s_id": "1234"}'));\
```

```
const {handler} = require('./index')
const {generateSid} = require('./credentials_check');

async function invoke(body) {
    return await handler({body: JSON.stringify(body)});
}

async function run() {
    const body =  {
        html: "yay",
        s_id: generateSid()
    }

    return await invoke(body)
}

run().then((data) => console.log(data))
```



Documents

| Id   | name | created_at |
| ---- | ---- | ---------- |
| -    | -    | -          |



Sections

| id   | name | document_id | created_at |
| ---- | ---- | ----------- | ---------- |
|      |      |             |            |

Pragraphs

| id   | name | section_id | created_at |
| ---- | ---- | ---------- | ---------- |
|      |      |            |            |

