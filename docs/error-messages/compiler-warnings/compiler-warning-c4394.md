---
title: Derleyici Uyarısı C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: 00c9e139e920473590389c05f076a7cd91a4fb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548859"
---
# <a name="compiler-warning-c4394"></a>Derleyici Uyarısı C4394

'function': per-appdomain simgesi __declspec(dllexport) ile işaretlenmemelidir

Bir işlev ile işaretlenen [appdomain](../../cpp/appdomain.md) `__declspec` değiştiricisi derlenmiş MSIL (için yerel) ve dışarı aktarma tabloları ([dışarı](../../windows/export.md) `__declspec` değiştiricisi) yönetilen işlevleri için desteklenmez.

Genel erişilebilirlik için yönetilen bir işlev bildirebilirsiniz. Daha fazla bilgi için [türü görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [üye görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).

C4394 her zaman hata olarak verilir.  Bu uyarı ile kapatabilirsiniz `#pragma warning` veya **/wd**; bkz [uyarı](../../preprocessor/warning.md) veya [/w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md)daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4394 oluşturur.

```
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```