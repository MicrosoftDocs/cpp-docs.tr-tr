---
title: Bağlayıcı araçları hatası LNK1306 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc007a4a594c8593d7820365377f1c811b1e23c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050573"
---
# <a name="linker-tools-error-lnk1306"></a>Bağlayıcı Araçları Hatası LNK1306

> DLL giriş noktası işlevi yönetilemez; Yerel derleme

`DllMain` MSIL olarak derlenemiyor; Yerelden derlenmelidir.

Bu sorunu çözmek için

- Olmadan giriş noktasını içeren dosyanın derleme **/CLR**.

- Giriş noktası koymak bir `#pragma unmanaged` bölümü.

Daha fazla bilgi için bkz.:

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [managed, unmanaged](../../preprocessor/managed-unmanaged.md)

- [Karışık Derlemeleri Başlatma](../../dotnet/initialization-of-mixed-assemblies.md)

- [DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK1306 oluşturur.

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

Bu sorunu gidermek için/CLR seçeneği bu dosyayı derleyin veya bunları kullanmanızı kullanmayın bir `#pragma` yönergesi, bu örnekte gösterildiği gibi yönetilmeyen bir bölümde giriş noktası tanımı koymak için:

```cpp
// LNK1306fix.cpp
// compile with: /clr /link /dll /entry:NewDllMain
#include <windows.h>
#pragma managed(push, off)
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
#pragma managed(pop)
```
