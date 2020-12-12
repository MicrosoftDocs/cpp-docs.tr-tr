---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4936'
title: Derleyici Uyarısı C4936
ms.date: 11/04/2016
f1_keywords:
- C4936
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
ms.openlocfilehash: e12cb789d3d008ec61672591cde78f1b7dc61da6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314990"
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
