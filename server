// server.js
const express = require('express');
const cors = require('cors');
const app = express();
app.use(cors());
app.use(express.json());

let temperature = 25;
let charging = true;

function randomVoltage() {
  return (220 + Math.random() * 5).toFixed(2);
}

function randomCurrent() {
  return (1 + Math.random() * 0.5).toFixed(2);
}

app.get('/status', (req, res) => {
  res.json({
    temperature,
    voltage: randomVoltage(),
    current: randomCurrent(),
    charging
  });
});

app.post('/increase-temp', (req, res) => {
  temperature++;
  res.json({ temperature });
});

app.post('/decrease-temp', (req, res) => {
  temperature--;
  res.json({ temperature });
});

app.post('/toggle-charging', (req, res) => {
  charging = !charging;
  res.json({ charging });
});

app.listen(5000, () => console.log('Backend running on port 5000'));
