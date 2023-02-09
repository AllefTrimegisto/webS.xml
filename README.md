# webS.xml

Uma empresa precisa se comunicar com outras para enviar informações pessoais sobre seus clientes, como nome, endereço e número de telefone. É importante garantir a segurança desses dados e se preocupar com quem eles são compartilhados. 
Para isso, crie a estrutura de um web service, que demonstra exemplos de comunicação SOAP

const express = require('express');
const bodyParser = require('body-parser');
const app = express();

app.use(bodyParser.text({type: 'text/xml'}));

app.post('/soap', (req, res) => {
  console.log(req.body);
  res.type('application/xml');
  res.status(200).send('<?xml version="1.0" encoding="UTF-8"?><soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/"><soap:Body><Response>Success</Response></soap:Body></soap:Envelope>');
});

app.listen(8080, () => {
  console.log('SOAP server listening on port 8080!');
});
