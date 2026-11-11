Personalização de Combos — Bridge e AdapterProjeto prático em JavaScript (Node.js) aplicando os padrões de projeto GoF Bridge e Adapter.🚀 Como ExecutarRequisito: Node.js 18+ (sem dependências externas).# Executar a demonstração
npm start

# Executar os testes
npm test
📐 Padrões Utilizados1. BridgeSepara a abstração do combo da implementação dos acompanhamentos (src/bridge.js). Permite trocar o lanche e os acompanhamentos (bebida e batata) dinamicamente sem recriar o combo.2. AdapterAdapta o SistemaLegadoBebidas (src/legado.js) para a interface padrão Bebida (src/itens.js) através do BebidaLegadaAdapter (src/adapter.js).📁 Estrutura do CódigoPadrão / PapelClasseArquivoBridge / AbstraçãoCombo / ComboPersonalizadosrc/bridge.jsBridge / ImplementaçãoAcompanhamentosPersonalizaveissrc/bridge.jsAdapter / AdaptadorBebidaLegadaAdaptersrc/adapter.jsLegado / AdapteeSistemaLegadoBebidassrc/legado.js💡 Exemplo de Usoconst bebida = new BebidaLegadaAdapter(new SistemaLegadoBebidas(), 202);
const combo = new ComboPersonalizado(
  1, 
  new McFish(), 
  new AcompanhamentosPersonalizaveis(bebida, new BatataFrita('média'))
);

console.log(combo.descricao());
// Saída: Combo 1: McFish | Suco 500 ml | Batata frita média
