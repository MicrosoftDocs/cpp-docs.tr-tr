---
title: Derleyici Uyarısı C4958
ms.date: 11/04/2016
f1_keywords:
- C4958
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
ms.openlocfilehash: 63371d91367902c1eab539cb370e55440fcbf917
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164891"
---
# <a name="compiler-warning-c4958"></a>Derleyici Uyarısı C4958

> '*Operation*': işaretçi aritmetiği doğrulanabilir değil

## <a name="remarks"></a>Açıklamalar

İşaretçi aritmetiği kullanmak doğrulanamayan bir görüntü oluşturur.

Daha fazla bilgi için bkz. [saf ve Doğrulanabilen kodC++(/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/Clr: Safe** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Bu uyarı bir hata olarak verilir ve [Uyarı](../../preprocessor/warning.md) pragması veya [/WD](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği ile devre dışı bırakılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4958 oluşturur:

```cpp
// C4958.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )
using namespace System;

int main( ) {
   Int32 arr[] = new Int32[10];
   Int32* p = &arr[0];
   p++;   // C4958
}
```

Derleyici, işaretçi aritmetiği ile dizi işlemlerini uygular. Bu nedenle, yerel diziler doğrulanabilir değildir; Bunun yerine bir CLR dizisi kullanın. Daha fazla bilgi için bkz. [dizi](../../extensions/arrays-cpp-component-extensions.md).

Aşağıdaki örnek C4958 oluşturur:

```cpp
// C4958b.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )

int main() {
   int array[5];
   array[4] = 0;   // C4958
}
```
