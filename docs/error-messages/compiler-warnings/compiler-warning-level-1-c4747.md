---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4747'
title: Derleyici Uyarısı (düzey 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: e182f4fc6a270917bb0b7e348000a0f084183ba6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332210"
---
# <a name="compiler-warning-level-1-c4747"></a>Derleyici Uyarısı (düzey 1) C4747

Yönetilen ' EntryPoint ' çağrılıyor: yönetilen kod DLL giriş noktası ve DLL giriş noktasından ulaşılan çağrılar dahil olmak üzere yükleyici kilidi altında çalışmayabilir

Derleyici MSIL 'ye derlenen bir (olası) DLL giriş noktası buldu.  Giriş noktası MSIL 'e derlenmiş bir DLL yükleme ile ilgili olası sorunlar nedeniyle, bir DLL giriş noktası işlevini MSIL 'e derlerken kesinlikle önerilmez.

Daha fazla bilgi için bkz. [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md) ve [BAĞLAYıCı araçları hata LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Modülü **/clr** ile derlenemiyor.

1. Giriş noktası işlevini ile işaretleyin `#pragma unmanaged` .

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
