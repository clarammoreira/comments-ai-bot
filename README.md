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

```javascript
// O objeto se users não existe nessa branch, mas existe na development
```

- 103: toast: { contentLoad: "Falha ao carregar os dados" } foi removido; pode ocasionar falta de mensagens de erro.

```javascript
// Esse objeto não existe mais no código
```

- 70: Adição de quebra de linha excessiva na string copyCode, o que pode dificultar manutenção do código.

```javascript
// Acredito que ela quebrou a linha porque a frase é longa

copyCode:
  "Copie o código do contrato no botão abaixo ou envie para o email da escola informado no contrato.",
```

- 119: Inconsistência na tradução: Consultant foi traduzido para "consultor" enquanto UF mantém a sigla em português.

```javascript
// Bem observado! No arquivo pt-BR.ts, algumas variáveis estão em português.
// Esse objeto contractCreate, por exemplo, está quase todo em português

contractCreate: {
  label: {
    consultant: "Nome consultor  *",
    time: "Tempo de vigência  *",
    schoolName: "Nome da instituição *",
    fantasyName: "Nome fantasia *",
    cnpj: "CNPJ *",
    mecCode: "Código MEC *",
    cep: "CEP *",
    cidade: "Cidade *",
    bairro: "Bairro *",
    uf: "UF *",
    endereco: "Endereço *",
    numero: "Número *",
    complemento: "Complemento",
    email: "Email do Representante *",
    telefone: "Telefone *",
    total_alunos: "Total de Alunos *",
    tipo_escola: "Tipo de Escola *",
    faturamento: "Faturamento Anual *",
  },
  input: {
    schoolName: "Digite o nome da instituição",
    fantasyName: "Digite o nome fantasia",
    cnpj: "Digite o CNPJ da empresa",
    mecCode: "Digite o código MEC",
    cep: "Digite o CEP",
    cidade: "Digite a cidade",
    bairro: "Digite o nome do bairro",
    uf: "PE",
    endereco: "Digite o endereço",
    numero: "Digite o número",
    complemento: "Digite um complemento",
    email: "Digite o email do representante",
    telefone: "Digite o telefone",
    total_alunos: "Selecione o total de alunos",
  },
  ...
}
```

- 117: Duplicação de chave consultant em generalData.label e generalData.input; pode causar problemas na renderização.
- 141: total_alunos foi traduzido incorretamente após alteração duplicada.

```javascript
// Realmente, total_alunos está em português, mas não está duplicado.
// As 2 ocorrências estão dentro de objetos diferentes.
// Uma está dentro do objeto label e a outra dentro de input 
```

- 144: cidade vs. city e bairro vs. neighborhood: alterar para uniformidade.

```javascript
// Faz sentido (OK)
```

- 282: Inconsistência nos rótulos, alguns foram modificados para inglês: profile em userDropdown enquanto outros permanecem em português.

```javascript
// Faz sentido (OK)
```

- 373: Bug na duplicação dos dados users causados pela remoção e adição. 

```javascript
// Nessa branch, o objeto users não existe
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

### ➡︎ pages/contracts/create/create.spec.js
- 35: falta importação omissa import { it } from "vitest"

```javascript
import {beforeEach, describe, vi} from "vitest";
```

- 37: uso constante desnecessário de flushPromises, utilize uma vez após modificar wrapper.vm.step
```javascript
// Nesse arquivo, é usada 6 vezes. Essas 4 abaixo, mais 2.

  it("should return to previous step when the 'return' and keep the 'advance' button without disabled", async () => {
    wrapper.vm.isNextStepDisabled = false;
    await flushPromises();

    await wrapper.findByTestId("advance-button", true).trigger("click");
    expect(wrapper.vm.step).toBe(1);
    await flushPromises();

    await wrapper.findByTestId("return-button", true).trigger("click");
    expect(wrapper.vm.step).toBe(0);

    await flushPromises();
    expect(wrapper.findByTestId("advance-button", true).attributes("disabled")).toBeUndefined();
  });
```

- 41: a busca pelo botão de 'avançar' pode ser feita sem true, ou precisa ser descrito exatamente como o seletor de teste
- 42: a busca pelo botão de 'retorna' pode ser feita sem true, ou precisa ser descrito exatamente como seletor de teste

```javascript
 it("should initialize with the 'advance' button disabled and without 'return' button", () => {
    expect(wrapper.findByTestId("advance-button", true).attributes("disabled")).toBeDefined();
    expect(wrapper.findByTestId("return-button", true).exists()).toBe(false);
  });
```

- 63: remova o teste duplicado do botão de voltara

```javascript
it("should return to previous step when the 'return' button is clicked and step is higher than 0", async () => {
  wrapper.vm.isNextStepDisabled = false;

  await flushPromises();
  await wrapper.findByTestId("advance-button", true).trigger("click");
  expect(wrapper.vm.step).toBe(1);

  await flushPromises();
  await wrapper.findByTestId("return-button", true).trigger("click");
  expect(wrapper.vm.step).toBe(0);

});

it("should return to previous step when the 'return' and keep the 'advance' button without disabled", async () => {
  wrapper.vm.isNextStepDisabled = false;
  await flushPromises();

  await wrapper.findByTestId("advance-button", true).trigger("click");
  expect(wrapper.vm.step).toBe(1);
  await flushPromises();

  await wrapper.findByTestId("return-button", true).trigger("click");
  expect(wrapper.vm.step).toBe(0);

  await flushPromises();
  expect(wrapper.findByTestId("advance-button", true).attributes("disabled")).toBeUndefined();
});
```

### ➡︎ pages/contracts/create/generalData/GeneralData.vue
- 6: "contractCreate.generalData.consultantData" foi alterado para "contractCreate.generalData.title_consultant", o que pode não refletir a intenção original.

```javascript
// Foi criado um título para cada section. title_consultant é um deles
// O consultantData é um array de objetos com os dados de cada input da section
// São coisas diferentes

  title_consultant:"Dados do consultor",
  title_institutionalData:"Dados do Institucionais",
  title_adress:"Localização",
  title_infoGeral:"Informações Gerais",
```

- 9: A classe "bg-blac" foi removida. Verifique se é necessário manter.

```javascript
// Essa classe não existe mais no projeto
```

- 19: "consultantData" foi alterado para "ConsultantData", o que pode causar erro caso a variável não tenha sido renomeada.

```javascript
// Foi alterado de camelCase para PascalCase (OK)
```

- 22: "input.id" foi alterado para "input.testId". Certifique-se de que todos os inputs possuem a propriedade "testId".

```javascript
// Os inputs tem essa propriedade

const ConsultantData = [
  {
    label: "contractCreate.generalData.label.consultant",
    testId: "consultant-select",
    placeholder: "contractCreate.generalData.select.consultant",
    items: ["João da Silva", "Pedro de Souza", "Maria de Lima"],
    modelValue: ref(null),
  },
  {
    label: "contractCreate.generalData.label.time",
    testId: "tempo-vigencia-select",
    placeholder: "contractCreate.generalData.select.time",
    items: [" 1", " 2", " 3"],
    modelValue: ref(null),
  },
];
```
