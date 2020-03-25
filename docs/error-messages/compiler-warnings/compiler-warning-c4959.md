---
title: Derleyici Uyarısı C4959
ms.date: 11/04/2016
f1_keywords:
- C4959
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
ms.openlocfilehash: 13d2ed705bff7b42eb3c348692a5829bd54158b0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164878"
---
# <a name="compiler-warning-c4959"></a>Derleyici Uyarısı C4959

> '*Type*' yönetilmeyen yapısı, üyelerine erişim doğrulanamayan kodu sağladığından/clr: Safe içinde tanımlanamaz

## <a name="remarks"></a>Açıklamalar

Yönetilmeyen bir türün üyesine erişmek doğrulanamayan bir (Peverify. exe) görüntüsü oluşturur.

Daha fazla bilgi için bkz. [saf ve Doğrulanabilen kodC++(/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/Clr: Safe** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Bu uyarı bir hata olarak verilir ve [Uyarı](../../preprocessor/warning.md) pragması veya [/WD](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği ile devre dışı bırakılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4959 oluşturur:

```cpp
// C4959.cpp
// compile with: /clr:safe

// Uncomment the following line to resolve.
// #pragma warning( disable : 4959 )
struct X {
   int data;
};

int main() {
   X x;
   x.data = 10;   // C4959
}
```
