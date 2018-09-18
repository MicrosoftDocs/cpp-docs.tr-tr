---
title: Bağlayıcı araçları hatası LNK1107 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73a1643d10ea9adc6ac6979eb2de023593ba8d01
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060713"
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