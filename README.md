# Comentários do bot

<b>Branch</b>: ✨ feat: #214 Perfil - Step 1 <br />
<b>Qtde. Comentários</b>: 84

### ➡ components/ContractActions.vue
- 21: variável router é indefinida resultando em erro ao tentar utilizar router.push

```javascript
@click="action.id === 2 && $router.push(`contract/${contract.id}/edit`)"
```

### ➡︎ components/RouteList.spec.js
- 1: a classe .toMatch deve ser substituída pela .toContain para verificar corretamente a existência da classe "v-list-item--active". <br />
- 5: mesmo comentário anterior

```javascript
it("should initialize with 'Dashboard route' option selected when active route is dashboard", () => {
  expect(wrapper.findComponent("[data-test-id=dashboard]").classes()).toMatch("v-list-item--active");
});

it("should initialize with 'Test route' option without active class", () => {
  expect(wrapper.findComponent("[data-test-id=test]").classes()).not.toMatch("v-list-item--active");
});
```

### ➡︎ components/TableContracts.vue
- 33: $router causa router não definido
- 41: router não utilizado após a declaração

```javascript
@click="$router.push('/contracts/create')"
```

- 113: largura de contractName não corresponde à nova largura

```javascript
{
  title: "Contratos",
  key: "contractName",
  align: "start",
  sortable: false,
  width: "30%",
},
```

- 118: alinhamento de status não corresponde ao novo alinhamento
- 123: alinhamento de creationDate não corresponde ao novo alinhamento
- 128: alinhamento de contractedValue não corresponde ao novo alinhamento

```javascript
{
  title: "Status",
  key: "status",
  align: "start",
  sortable: false,
  width: "12.5%",
},
{
  title: "Data de Criação",
  key: "creationDate",
  align: "start",
  sortable: false,
  width: "12.5%",
},
{
  title: "Valor Contratado",
  key: "contractedValue",
  align: "start",
  sortable: false,
  width: "12.5%",
},
```

### ➡︎ components/UserDropdown.vue
- 12: user[0].avatar deve ser alterado para user.avatar para manter a consistência com o código atualizado.
- 17: user[0].name deve ser alterado para user.name para manter a consistência com o código atualizado.
- 18: user[0].role deve ser alterado para user.role para manter a consistência com o código atualizado.

```javascript
// user.avatar, user.name e user.role já estão sendo utilizados no código
// user[0].avatar, user[0].name e user[0].role não existem 
```

### ➡︎ components/users/UserActions.spec.js
- 4: espaço ausente entre `{ }`
- 5: espaço em branco ausente após virgula "describe"
- 7: importação duplicada de "@vue/test-utils" e import * as componentes não utilizados
- 17: mock de useRouter não está sendo restaurado após os testes
- 21: mock de toggleUserStatus não está sendo restaurado após os testes
- 27: mock de provide.toast.show não está sendo restaurado após os testes
- 33: nome inconsistente no describe, "Product list screen" deveria refletir o teste de "User Actions"
- 68: falta de nova linha no final do arquivo

```javascript
// Esse arquivo não existe nessa branch (feat/TG-214)
```

### ➡︎ layouts/default.vue
- 97: importação de PhUsers permanece mas não é usada

```javascript
import {PhGear, PhHouse, PhList, PhFileText,PhUsers} from "@phosphor-icons/vue";

{
  key: "users",
  title: "users",
  path: "/users",
  icon: PhUsers
}
```

- 121-126: Remoção de página de users no componente atualizado, mas ainda definida na seção defaultPages

```javascript
// Página users não existe nessa branch, mas existe na development
```

### ➡︎ locales/pt-BR.ts
- 92: users bloco foi removido completamente causando dados de usuários a serem perdidos.
- 103: toast: { contentLoad: "Falha ao carregar os dados" } foi removido; pode ocasionar falta de mensagens de erro.
- 70: Adição de quebra de linha excessiva na string copyCode, o que pode dificultar manutenção do código.
- 119: Inconsistência na tradução: Consultant foi traduzido para "consultor" enquanto UF mantém a sigla em português.
- 117: Duplicação de chave consultant em generalData.label e generalData.input; pode causar problemas na renderização.
- 141: total_alunos foi traduzido incorretamente após alteração duplicada.
- 144: cidade vs. city e bairro vs. neighborhood: alterar para uniformidade.
- 282: Inconsistência nos rótulos, alguns foram modificados para inglês: profile em userDropdown enquanto outros permanecem em português.
- 373: Bug na duplicação dos dados users causados pela remoção e adição.
- 

```javascript
// O objeto se users não existe nessa branch, mas existe na development
```

### ➡︎ nuxt.config.ts
- 38: Remoção do plugin "maska" pode causar problemas se ele for utilizado em outros lugares do projeto

```javascript
// Provavelmente ele comparou essa branch, que não tem o plugin, com a development
```

### ➡︎ pages/contracts/create/contract/Contract.vue
- 109: contracResume está incorretamente escrito (presumivelmente deveria ser contractResume)

```javascript
// Realmente, na development existe essa variável. Ela é declarada e utilizada com esse nome, por isso não deu erro. (OK)
```

- 153: utilização incorreta de ref (deveria ser chamada nas declarações de variáveis dentro das listas de objetos contractData, checkoutConfig e contractResume)

```javascript
// Realmente, essas variáveis são declaradas sem o ref (OK)

const contractData = [
  {
    id: "salesPrice",
    label: "contractCreate.contract.label.salesPrice",
    placeholder: "contractCreate.contract.input.salesPrice",
    type: "text",
    modelValue: ref("")
  },
...
]

const checkoutConfig = {
  id: "paymentType",
  label: "contractCreate.contract.label.paymentType",
  placeholder: "contractCreate.contract.select.paymentType",
  items: [" 1", " 2", " 3"],
  modelValue: ref(null)
};

const contracResume = [
  {
    id: "observation",
    label: "contractCreate.contract.label.observation",
    placeholder: "contractCreate.contract.input.observation",
    type: "text",
    modelValue: ref("")
  },
  ...
]
```

### ➡︎
-

```javascript
```
