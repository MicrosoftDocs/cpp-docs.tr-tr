---
title: Bağlayıcı Araçları Hatası LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: 68048d9f824283d002a4ea8b64d88f37bbeefc48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646569"
---
# <a name="linker-tools-error-lnk1107"></a>Bağlayıcı Araçları Hatası LNK1107

dosya geçersiz veya bozuk: konumda okunamıyor

Araç dosyası okunamadı. Dosyayı yeniden oluşturun.

LNK1107 bir modül geçirmeye çalışırsanız da olabilir (.dll veya .netmodule uzantısı ile oluşturulan [/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) veya [noassembly](../../build/reference/noassembly-create-a-msil-module.md)) bağlayıcıya; bunun yerine .obj dosyasına geçirin.

Aşağıdaki örnek derlerseniz:

```
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

ve ardından belirtin **LNK1107.dll bağlantı** komut satırında LNK1107 alırsınız.  Hatayı gidermek için belirtin **LNK1107.obj bağlantı** yerine.