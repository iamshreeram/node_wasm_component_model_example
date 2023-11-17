# Running wasm in js 

### List of steps to run the wasm 


```
git clone 
cd node_wasm_component_model_example
npm install
```


Creates the component  
```
node componentize.mjs
```

Building the component and running it in wasmtime 
```
cargo build --release
./target/release/wasmtime-test
```

#### Transpiling wasm to js
```
jco transpile hello.component.wasm -o hello --map 'wasi-*=@bytecodealliance/preview2-shim/*' 
```


```
node -e "import('./hello/hello.component.js').then(m => console.log(m.hello('ComponentizeJS')))"
```

