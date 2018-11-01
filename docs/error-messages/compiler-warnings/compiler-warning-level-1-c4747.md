---
title: Derleyici Uyarısı (düzey 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: ecaabd482049771b1d3915470a2be7a52e36d361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462393"
---
# <a name="compiler-warning-level-1-c4747"></a>Derleyici Uyarısı (düzey 1) C4747

Çağırma yönetilen 'giriş noktası': yönetilen kod DLL giriş noktası ve DLL giriş noktasından ulaşılan çağrılar dahil olmak üzere, yükleyici kilidi altında çalışmayabilir

Derleyici, MSIL olarak derlenmiş (olası) bir DLL giriş noktası bulunamadı.  Giriş noktası MSIL olarak derlenmiş bir DLL yükleme ile ilgili olası sorunları nedeniyle MSIL DLL giriş noktası işleve derlenmesini kesinlikle önerilmez.

Daha fazla bilgi için [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md) ve [Bağlayıcı araçları hatası LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Modülüyle derlenmiyor **/CLR**.

1. Giriş noktası işlevini ile işaretle `#pragma unmanaged`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4747 oluşturur.

```
// C4747.cpp
// compile with: /clr /c /W1
// C4747 expected
#include <windows.h>

// Uncomment the following line to resolve.
// #pragma unmanaged

BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {
   return TRUE;
};
```