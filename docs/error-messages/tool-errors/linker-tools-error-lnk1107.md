---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1107'
title: Bağlayıcı Araçları Hatası LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: 2a5ed9ba0bc4789a324d143b6287a08712299cdd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281398"
---
# <a name="linker-tools-error-lnk1107"></a>Bağlayıcı Araçları Hatası LNK1107

dosya geçersiz veya bozuk: konum okunamıyor

Araç dosyayı okuyamadı. Dosyayı yeniden oluşturun.

LNK1107 Ayrıca, bağlayıcıya ( [/clr: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) veya  [/noAssembly](../../build/reference/noassembly-create-a-msil-module.md)ile oluşturulmuş bir modül) (. dll veya. netmodule uzantısı) bağlayıcıya geçirmeye çalıştığınızda da gerçekleşebilir; Bunun yerine. obj dosyasını geçirin.

Aşağıdaki örneği derlerseniz:

```cpp
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

ardından, komut satırında **bağlantı LNK1107.dll** BELIRTIN, LNK1107 alacaksınız.  Hatayı gidermek için bunun yerine **LINK LNK1107. obj** ' i belirtin.
