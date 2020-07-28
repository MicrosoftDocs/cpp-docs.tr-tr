---
title: Derleyici Uyarısı C4936
ms.date: 11/04/2016
f1_keywords:
- C4936
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
ms.openlocfilehash: 9b1c3d1de662451432fe4fa0f058c503dc1f7b39
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220125"
---
# <a name="compiler-warning-c4936"></a>Derleyici Uyarısı C4936

> Bu __declspec yalnızca/CLR veya/clr: Pure ile derlendiğinde desteklenir

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

**`__declspec`** Değiştirici kullanıldı, ancak bu **`__declspec`** değiştirici yalnızca [/clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneklerinden biri ile derlendiğinde geçerlidir.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [Process](../../cpp/process.md).

C4936 her zaman bir hata olarak verilir.  C4936 [Uyarı](../../preprocessor/warning.md) pragması ile devre dışı bırakabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4936 oluşturur:

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```
