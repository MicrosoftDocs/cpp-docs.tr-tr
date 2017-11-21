---
title: "Bağlayıcı araçları hatası LNK1306 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1306
dev_langs: C++
helpviewer_keywords: LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d020d7ca037c737dfb03c32ff2d773730c118311
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1306"></a>Bağlayıcı Araçları Hatası LNK1306  
  
> DLL giriş noktası işlevi yönetilemez; Yerel derleme  
  
`DllMain`MSIL için derlenemez; Yerel derlenmelidir.  
  
Bu sorunu gidermek için  
  
-   Giriş noktası olmadan içeren dosyanın derleme **/CLR**.  
  
-   Giriş noktası yerleştirecek bir `#pragma unmanaged` bölümü.  
  
Daha fazla bilgi için bkz.:  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md)  
  
-   [Karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md)  
  
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
  
Bu sorunu gidermek için/CLR seçeneği bu dosyayı derlemeye veya kullanmak için kullanmayın bir `#pragma` yönergesi Bu örnekte gösterildiği gibi bir yönetilmeyen bölümünde giriş noktası tanımı yerleştirilecek:  
  
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
