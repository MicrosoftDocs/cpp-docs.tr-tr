---
title: Derleyici Uyarısı C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: ad6b9624a1bf510465843167d104d1bec189bc70
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197364"
---
# <a name="compiler-warning-c4394"></a>Derleyici Uyarısı C4394

' function ': per-AppDomain simgesi __declspec (dllexport) ile işaretlenmemelidir

[AppDomain](../../cpp/appdomain.md) değiştiricisi ile işaretlenmiş BIR işlev **`__declspec`** MSIL (yerel değil) olarak derlenir ve dışarı aktarma tabloları ([dışarı aktarma](../../windows/export.md) **`__declspec`** değiştiricisi) yönetilen işlevler için desteklenmez.

Yönetilen bir işlevi, genel erişilebilirliği olacak şekilde bildirebilirsiniz. Daha fazla bilgi için bkz. [tür görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [üye görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).

C4394 her zaman bir hata olarak verilir.  Bu uyarıyı `#pragma warning` veya **/WD**ile devre dışı bırakabilirsiniz; daha fazla bilgi için bkz. [Warning](../../preprocessor/warning.md) veya [/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4394 oluşturur.

```cpp
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```
