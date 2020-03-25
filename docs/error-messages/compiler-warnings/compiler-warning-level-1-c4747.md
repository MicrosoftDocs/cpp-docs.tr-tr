---
title: Derleyici Uyarısı (düzey 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: 2fd7f0960966a981d82d19e7b2533b1ffcd3bc00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175200"
---
# <a name="compiler-warning-level-1-c4747"></a>Derleyici Uyarısı (düzey 1) C4747

Yönetilen ' EntryPoint ' çağrılıyor: yönetilen kod DLL giriş noktası ve DLL giriş noktasından ulaşılan çağrılar dahil olmak üzere yükleyici kilidi altında çalışmayabilir

Derleyici MSIL 'ye derlenen bir (olası) DLL giriş noktası buldu.  Giriş noktası MSIL 'e derlenmiş bir DLL yükleme ile ilgili olası sorunlar nedeniyle, bir DLL giriş noktası işlevini MSIL 'e derlerken kesinlikle önerilmez.

Daha fazla bilgi için bkz. [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md) ve [BAĞLAYıCı araçları hata LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Modülü **/clr**ile derlenemiyor.

1. Giriş noktası işlevini `#pragma unmanaged`işaretleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4747 oluşturur.

```cpp
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
