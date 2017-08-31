##  以太坊相关

### Geth
==================
关于geth 1.6 没法使用solidity 内嵌的编译 <br>
解决方法 <br>
1. 生产 bytecode: <br>
  solc -o ./ --bin xxx.sol  <br>
2. 生产 abi: <br>
  solc -o ./ --abi xxx.sol  <br>

修改 xxx.bin  , xxx.abi <br>

3. 使用步骤 <br>
  loadScript("/path/to/xxx.bin") <br>
  loadScript("/path/to/xxx.abi") <br>
  myContract = eth.contract(abi) <br>
  myDeploy = {from:eth.coinbase, data: bytecode, gas: 1000000} <br>
  myContInst = myContract.new(txDeploy) <br>

  //启动挖矿 <br>
  
  myInst = myContract.at(myContInst.address) <br>
  
  //调用 <br>
  myInst.<function>.call(argv, ....)  // function 函数名 <br>
  
参考： https://ethereum.stackexchange.com/questions/15435/how-to-compile-solidity-contracts-with-geth-v1-6/15436 <br>
      http://blog.csdn.net/jwter87/article/details/53445709 <br>
      http://blog.csdn.net/CHENYUFENG1991/article/details/53458175?locationNum=7&fps=1 <br>
      

### 关于solc 使用
==================

参考： https://zhuanlan.zhihu.com/p/27889205 <br>
      Solidity 简易教程: http://wiki.jikexueyuan.com/project/solidity-zh/introduction.html <br> 