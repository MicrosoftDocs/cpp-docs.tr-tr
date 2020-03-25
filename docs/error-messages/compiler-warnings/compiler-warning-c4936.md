---
title: Derleyici Uyarısı C4936
ms.date: 11/04/2016
f1_keywords:
- C4936
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
ms.openlocfilehash: c6d54cf8b6704eec2a9e6af890c5c80c67106995
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165008"
---
# <a name="compiler-warning-c4936"></a>Derleyici Uyarısı C4936

> Bu __declspec yalnızca/CLR veya/clr: Pure ile derlendiğinde desteklenir

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

`__declspec` değiştiricisi kullanıldı, ancak bu `__declspec` değiştirici yalnızca [/clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneklerinden biri ile derlendiğinde geçerlidir.

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
