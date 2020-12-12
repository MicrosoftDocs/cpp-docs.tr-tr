---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1306'
title: Bağlayıcı Araçları Hatası LNK1306
ms.date: 11/04/2016
f1_keywords:
- LNK1306
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
ms.openlocfilehash: aa6386da7c836eea8365d8a4ffde0bbd80d0fa81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193662"
---
# <a name="linker-tools-error-lnk1306"></a>Bağlayıcı Araçları Hatası LNK1306

> DLL giriş noktası işlevi yönetilemez; Yerel olarak derle

`DllMain` MSIL 'e derlenemiyor; Yerel olarak derlenmesi gerekir.

Bu sorunu çözmek için,

- Giriş noktasını içeren dosyayı **/clr** olmadan derleyin.

- Giriş noktasını bir `#pragma unmanaged` bölüme koyun.

Daha fazla bilgi için bkz:

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [managed, unmanaged](../../preprocessor/managed-unmanaged.md)

- [Karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md)

- [DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1306 oluşturur.

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

Bu sorunu onarmak için, bu dosyayı derlemek için/clr seçeneğini kullanmayın veya `#pragma` giriş noktası tanımını Bu örnekte gösterildiği gibi yönetilmeyen bir bölüme koymak için bir yönerge kullanın:

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
