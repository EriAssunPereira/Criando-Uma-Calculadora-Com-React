# Criando-Uma-Calculadora-Com-React

Criar uma calculadora com React é uma ótima maneira de aplicar e aprofundar seus conhecimentos em desenvolvimento de interfaces de usuário. Aqui está um exemplo de como podemos começar a estruturar esse projeto:

```jsx
import React, { useState } from 'react';

// Componente Display para mostrar os resultados
const Display = ({ value }) => (
  <div className="display">{value}</div>
);

// Componente Button para os botões da calculadora
const Button = ({ label, onClick }) => (
  <button onClick={onClick}>{label}</button>
);

// Componente Keypad para o teclado da calculadora
const Keypad = ({ onInput }) => (
  <div className="keypad">
    {/* Você pode adicionar mais botões conforme necessário */}
    <Button label="1" onClick={() => onInput('1')} />
    <Button label="2" onClick={() => onInput('2')} />
    {/* ... */}
  </div>
);

// Componente principal Calculator
const Calculator = () => {
  const [value, setValue] = useState('');

  // Função para lidar com a entrada dos botões
  const handleInput = (input) => {
    setValue(value + input);
  };

  return (
    <div className="calculator">
      <Display value={value} />
      <Keypad onInput={handleInput} />
    </div>
  );
};

export default Calculator;
```

**Dicas Importantes:**
- **Estado e Lógica:** Utilize o hook `useState` para gerenciar o estado da calculadora, como o valor atual exibido e os cálculos.
- **Componentização:** Divida sua aplicação em componentes menores para facilitar a manutenção e o reuso de código.
- **Estilização:** Aplique CSS para melhorar a aparência da sua calculadora. Você pode usar módulos CSS ou styled-components para estilos mais complexos.

Lembre-se de testar cada funcionalidade à medida que você desenvolve. Isso ajuda a identificar e corrigir problemas mais rapidamente. 

Para adicionar operações de cálculo à sua calculadora, você pode seguir estas etapas:

1. **Defina os botões de operação:**
   - Adicione botões para as operações matemáticas, como adição, subtração, multiplicação e divisão.
   - Por exemplo, você pode criar botões com os símbolos "+", "-", "*", "/".
   - Cada botão deve ter uma função associada que atualiza o estado da calculadora com a operação selecionada.

2. **Implemente a lógica das operações:**
   - Crie funções para realizar as operações matemáticas com base nos valores inseridos.
   - Por exemplo, quando o usuário pressionar o botão de adição, você pode somar os valores atuais na tela com o próximo valor inserido.
   - Mantenha o controle do estado da calculadora (valor atual, operação selecionada etc.) usando o hook `useState`.

3. **Exiba os resultados:**
   - Atualize o display da calculadora com o resultado da operação.
   - Por exemplo, se o usuário pressionar "=" após inserir os números e a operação, calcule o resultado e mostre-o no display.

Aqui está um exemplo simplificado de como você pode adicionar a operação de adição à sua calculadora:

```jsx
// Componente Button para os botões da calculadora
const Button = ({ label, onClick }) => (
  <button onClick={onClick}>{label}</button>
);

// ...

// Função para lidar com a entrada dos botões
const handleInput = (input) => {
  if (input === '=') {
    // Realize a operação com base no estado atual (exemplo: adição)
    // Atualize o estado com o resultado
  } else {
    // Atualize o estado com o número ou operação selecionada
  }
};
```

Lembre-se de adaptar essa lógica para as outras operações (subtração, multiplicação, divisão) e testar cada funcionalidade à medida que você desenvolve.

https://github.com/digitalinnovationone/trilha-react-desafio01-calculadora
