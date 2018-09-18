---
title: Bağlayıcı araçları hatası LNK1237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9ada38fcf3a706f7852f49f60f677fb5dc10d7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065302"
---
# <a name="linker-tools-error-lnk1237"></a>Bağlayıcı Araçları Hatası LNK1237

kod oluşturma sırasında derleyici, /GL ile derlenmiş'module ' modülünde tanımlanan'symbol ' sembole başvuru sunulan

Kod oluşturma sırasında derleyici derlenmiş tanımlarını daha çözümlenir simgeleri tanımlamak İstemediğimiz **/GL**. `symbol` tanıtılan ve daha sonra ile derlenmiş bir tanımı çözümlendi bir sembol **/GL**.

Daha fazla bilgi için [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).

Simgesiyle LNK1237 çözmek için derlenmiyor **/GL** veya [/Include (simge başvurularını zorla)](../../build/reference/include-force-symbol-references.md) sembole bir başvuru zorlamak için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK1237 oluşturur. Bu hatayı gidermek için değil dizideki LNK1237_a.cpp başlatmak ve eklemek **/ include: __chkstk** bağlantı komutu.

```
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```