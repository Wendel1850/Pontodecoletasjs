
const cep = '01001-000'; // substitua pelo CEP desejado
const url = `https://viacep.com.br/ws/${cep}/json/`;

fetch(url)
  .then(response => response.json())
  .then(data => {
    console.log(data);
    const endereco = {
      logradouro: data.logradouro,
      bairro: data.bairro,
      cidade: data.localidade,
      estado: data.uf,
      cep: data.cep
    };
    console.log(endereco);
  })
  .catch(error => console.error(error));
