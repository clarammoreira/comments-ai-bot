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

### ➡︎ 

```javascript
```

### ➡︎ 

```javascript
```



