---
title: Bağlayıcı Araçları Hatası LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: c56b2eb86c7605fb3330d7b1bb01e3235466ede6
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990966"
---
# <a name="linker-tools-error-lnk1237"></a>Bağlayıcı Araçları Hatası LNK1237

kod oluşturma sırasında, derleyici/GL ile derlenen ' Module ' modülünde tanımlanan ' symbol ' simgesine başvuru sunmuştur

Kod oluşturma sırasında derleyici, daha sonra derlenen **/GL**tanımlarına çözümlenen sembolleri sunmaz. `symbol`, daha sonra **/GL**ile derlenen bir tanıma çözümlenen ve daha sonra çözümlenmiş bir simgedir.

Daha fazla bilgi için bkz. [/GL (tüm program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).

LNK1237 çözümlemek için, simgeyi **/GL** ile derleyip ya da simgeye bir başvuru zorlamak için [/Include (sembol başvurularını zorla)](../../build/reference/include-force-symbol-references.md) kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1237 oluşturur. Bu hatayı çözmek için, diziyi LNK1237_a. cpp ' de başlatmayın ve bağlantı komutuna **/include: __chkstk** ekleyin.

```cpp
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```cpp
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```
