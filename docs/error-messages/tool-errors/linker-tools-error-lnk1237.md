---
title: Bağlayıcı Araçları Hatası LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: ae1a397cdcc10cd89fd046a94e78c15dd46dceed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242537"
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