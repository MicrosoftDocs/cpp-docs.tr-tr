---
title: Bağlayıcı Araçları Hatası LNK1306
ms.date: 11/04/2016
f1_keywords:
- LNK1306
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
ms.openlocfilehash: ddaa8797e0cf8ff617408aedc770b21cc656cec4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160464"
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
