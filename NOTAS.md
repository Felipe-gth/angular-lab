# Notas estudo angular

# Capítulo 1 - Visão geral:

### O que aprendi: Entender o basico da estrutura do projeto

### Onde travei e como saí: Procurando os services no arquivo, destravei abrindo a pasta services e vendo o que consumia eles.

### Pergunta em aberto: O que são modulos e componentes

## Exercicios

### Exercicio Facil: Rodar o projeto

### Exercicio Medio: 

#### Apresentante:
##### 1 Arquivo: mini-protesto\apresentante\apresentante.module.ts

##### 2 Rotas: linha 10 - 14

<pre>
  const routes: Routes = [
    { path: '',         component: ApresentanteListaComponent },
    { path: 'novo',     component: ApresentanteFormComponent  },
    { path: ':id/editar', component: ApresentanteFormComponent }
  ];
</pre>

##### 3 Componentes no declarations: no decorador NgModule (linha 16-19)

<pre>
  @NgModule({
    declarations: [ApresentanteListaComponent, ApresentanteFormComponent],
    imports: [CommonModule, ReactiveFormsModule, RouterModule.forChild(routes)]
  })
</pre>

##### 4 Services: Possui dois componentes - apresentante-form & apresentante-lista

<pre>
  - apresentante-form: linha 4
  
  import { ApresentanteService } from '../services/apresentante.service';
  
  
  - apresentante-lista: linha 3
  
  import { ApresentanteService } from '../services/apresentante.service';
</pre>

#### Intimacao:
##### 1 Arquivo: mini-protesto\apresentante\intimacao.module.ts

##### 2 Rotas: linha 8

<pre>const routes: Routes = [{ path: '', component: IntimacaoListaComponent }];</pre>

##### 3 Componentes no declarations: no decorador NgModule (linha 10-13)

<pre>
  @NgModule({
    declarations: [IntimacaoListaComponent],
    imports: [CommonModule, ReactiveFormsModule, RouterModule.forChild(routes)]
  })
</pre>

##### 4 Services: linha 6 intimacao.module.ts - duvida

<pre>import { IntimacaoListaComponent } from './intimacao-lista.component';</pre>



### Exercicio Dificil: 

#### Pontos em Comum:
<pre>
  1 - Os dois projetos têm o arquivo *.module.ts para cada modulo
  2 - Os dois projetos usam o mesmo padrão de estrutura e de arquitetura
  3 - OS dois projetos possuem app-routing.module.ts
</pre>

#### Pontos diferentes:
<pre>
1 - O projeto completo possui uma pasta shared com itens que são compartilhados entre os componentes especificamente para cada modulo, ja que possuem mais de um componente.
2 - Apenas o projeto completo possui o *-routing.module.ts, que serve para consumir as rotas, que depois vai ser importado pelo modulo principal, separado para organizar por ter mais de um componente por modulo
3 - Por ter mais de um componente, no projeto completo eles são separados em pastas, por regras de boas práticas e de estrutura
</pre>

---
