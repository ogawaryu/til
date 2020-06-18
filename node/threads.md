# Threads no Node.JS

Sim! a partir da versão 10.5.0 do node, foi implementado suporte a threads ainda em fase experimental e agora na versão 12 LTS, removeram flag experimental. Javacript sempre foi conhecido por ter uma unica thread, a main thread, e já algum tempo, temos suporte a multithreading.

E por que usar thread em node? Usar multithreading no javascript possibilita utilizar computação mais "pesada" que existe um grande processamento. Desse jeito, o node.JS abre portas para áreas da computação onde ele não tem tanta força, como data science e machine learning.

### Como usar Thread em Node

```javascript

const {
  Worker, isMainThread, parentPort, workerData
} = require('worker_threads')

if (isMainThread) {
  module.exports = function parseJSAsync(script) {
    return new Promise((resolve, reject) => {
      const worker = new Worker(__filename, {
        workerData: script
      });
      worker.on('message', resolve);
      worker.on('error', reject);
      worker.on('exit', (code) => {
        if (code !== 0)
          reject(new Error(`Worker stopped with exit code ${code}`))
      });
    });
  };
} else {
  const { parse } = require('some-js-parsing-library')
  const script = workerData
  parentPort.postMessage(parse(script))
}

```
