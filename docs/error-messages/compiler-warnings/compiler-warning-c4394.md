---
title: Derleyici Uyarısı C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: b97819a6f1b95f083eb594d3b9b2e68cbf30d19a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623688"
---
# <a name="compiler-warning-c4394"></a>Derleyici Uyarısı C4394

' function ': per-AppDomain simgesi __declspec (dllexport) ile işaretlenmemelidir

[Appdomain](../../cpp/appdomain.md)`__declspec` değiştiricisi ile işaretlenmiş bir Işlev, MSIL 'e (yerel olarak değil) derlenir ve dışarı aktarma tabloları ([dışarı aktarma](../../windows/export.md)`__declspec` değiştiricisi) yönetilen işlevler için desteklenmez.

Yönetilen bir işlevi, genel erişilebilirliği olacak şekilde bildirebilirsiniz. Daha fazla bilgi için bkz. [tür görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [üye görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).

C4394 her zaman bir hata olarak verilir.  Bu uyarıyı `#pragma warning` veya **/WD**; ile devre dışı bırakabilirsiniz. daha fazla bilgi için bkz. [Warning](../../preprocessor/warning.md) [;/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4394 oluşturur.

```cpp
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```