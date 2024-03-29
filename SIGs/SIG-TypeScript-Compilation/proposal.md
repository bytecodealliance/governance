# Proposal to Create SIG-TypeScript-Compilation

This document is a proposal to create SIG-TypeScript-Compilation as a formal Special Interest Group (SIG) under the auspices of the TSC of the Bytecode Alliance, as specified in the TSC’s charter. 

SIG-TypeScript-Compilation's primary goal is to describe and refine a suitable solution for compiling the TypeScript program to WebAssembly based on the Wasm GC proposal and executing it in both browser and standalone Wasm runtime. The scope of this SIG is limited to discussions about compiling TS to WebAssembly, the necessary runtime API (potentially defined as WASI) for supporting TS language features such as `Any` type, and exploration of how WebAssembly can grow to provide better support of dynamic languages natively.

While it is not an express goal of the group, it is understood that in the process of designing, the group will produce proof-of-concept code.   

As deliverables of the SIG, the group will produce Notes describing the scope of supported TS language features, the compilation methods, the runtime API definitions, and new proposals for WebAssembly or WASI spec. Should the TSC accept these Notes, the SIG will refine them into a position or recommendation. 

Should the code artifacts prove generally useful, the SIG may also approach the TSC about turning one or more of these efforts into a Core or At Large Project. As part of this process, the SIG will delegate some or all of its participants as maintainers of any code that will continue development after the SIG is complete. 

The SIG is not intended to fork the TypeScript language. This can be achieved by only supporting a strict subset of the language, or by ensuring that all language extensions (e.g. additions to the type system or standard library) are coordinated with the TypeScript core team and have a path to being upstreamed.

This SIG follows BA's common guideline as the TSC suggested: Any APIs or new instructions that a runtime exposes to Wasm must go through a standardization process, and achieve consensus in that process, and be sufficiently stable before they can be enabled by default in any runtime under the Bytecode Alliance's umbrella.



## Supporting Members 

The following individuals support the creation of SIG-TypeScript-Compilation: 
- Chen Wengang [@ApsarasX](https://github.com/ApsarasX) (Alibaba/Ant)
- Dima, Voytenko [@dvoytenko](https://github.com/dvoytenko) (Google)  
- Dong Junjie [@coderebot](https://github.com/coderebot) (Xiaomi)  
- Dong Weixin [@WeixinDong](https://github.com/WeixinDong) (OPPO)  
- Fan Shaogui [@GreatFan](https://github.com/GreatFan) (ByteDance)  
- He Jie [@jhe33](https://github.com/jhe33) (Alibaba/Ant)   
- Huang Qi [@no1wudi](https://github.com/no1wudi) (Xiaomi)  
- Huang Wenyong [@wenyongh](https://github.com/wenyongh) (Intel)  
- Jin Zhenwei [@zhenweijin](https://github.com/zhenweijin) (Intel)  
- Petr, Penzin [@penzn](https://github.com/penzn) (Intel)  
- Kolny, Marcin [@loganek](https://github.com/loganek) (Amazon)  
- Squillace, Ralph [@squillace](https://github.com/squillace) (Microsoft)
- Su Yihan [@yviansu](https://github.com/yviansu) (Intel)  
- Vivek, Sekhar [@vsekhar](https://github.com/vsekhar) (Google)
- Wang Xin [@xwang98](https://github.com/xwang98) (Intel)  
- Xiao Xiang [@xiaoxiang781216](https://github.com/xiaoxiang781216) (Xiaomi)  
- Xu Jun [@xujuntwt95329](https://github.com/xujuntwt95329) (Intel)  
- Xu Xiong[@venus-taibai](https://github.com/venus-taibai) (Alibaba/Ant)  
- Yang Wenming [@YoungWenMing](https://github.com/YoungWenMing) (ByteDance)  
- Yao Zhongxiao [@yaozhongxiao](https://github.com/yaozhongxiao) (ByteDance)  
- Zhang Di [@Zzzode](https://github.com/Zzzode) (ByteDance)  


