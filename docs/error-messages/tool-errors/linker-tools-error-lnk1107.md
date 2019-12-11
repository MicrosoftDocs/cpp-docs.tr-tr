---
title: Bağlayıcı Araçları Hatası LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: c75966d9c6c22f1bd2123fb30282bb2bed467130
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991035"
---
# <a name="linker-tools-error-lnk1107"></a>Bağlayıcı Araçları Hatası LNK1107

dosya geçersiz veya bozuk: konum okunamıyor

Araç dosyayı okuyamadı. Dosyayı yeniden oluşturun.

LNK1107 Ayrıca, bağlayıcıya ( [/clr: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) veya [/noAssembly](../../build/reference/noassembly-create-a-msil-module.md)ile oluşturulmuş bir modül) (. dll veya. netmodule uzantısı) bağlayıcıya geçirmeye çalıştığınızda da gerçekleşebilir; Bunun yerine. obj dosyasını geçirin.

Aşağıdaki örneği derlerseniz:

```cpp
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

ardından, komut satırında **LINK LNK1107. dll** ' yi BELIRTIN, LNK1107 alacaksınız.  Hatayı gidermek için bunun yerine **LINK LNK1107. obj** ' i belirtin.
