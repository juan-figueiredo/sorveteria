Sorveteria

Função para exibir o menu de sorvetes
function exibirMenu() {
  console.log("=== Menu de Sorvetes ===");
  console.log("1. Sorvete de Baunilha - R$3.50");
  console.log("2. Sorvete de Chocolate - R$4.00");
  console.log("3. Sorvete de Morango - R$4.50");
  console.log("=========================");
}

Função para processar o pedido do cliente
function fazerPedido(opcao) {
  let preco = 0;

  switch (opcao) {
    case 1:
      preco = 3.50;
      break;
    case 2:
      preco = 4.00;
      break;
    case 3:
      preco = 4.50;
      break;
    default:
      console.log("Opção inválida. Por favor, escolha um número do menu.");
      return;
  }

  console.log(`Você escolheu o sorvete. Valor a pagar: R$${preco.toFixed(2)}`);
  return preco;
}

// Função para processar o pagamento
function processarPagamento(valorTotal, valorPago) {
  if (valorPago >= valorTotal) {
    const troco = valorPago - valorTotal;
    console.log(`Pagamento efetuado com sucesso. Troco: R$${troco.toFixed(2)}`);
  } else {
    console.log("Pagamento insuficiente. Por favor, insira valor suficiente.");
  }
}

// Fluxo principal do programa
exibirMenu();
const opcaoEscolhida = parseInt(prompt("Escolha o número do sorvete desejado:"));
const totalAPagar = fazerPedido(opcaoEscolhida);

if (totalAPagar) {
  const valorPago = parseFloat(prompt("Insira o valor pago:"));
  processarPagamento(totalAPagar, valorPago);
}
