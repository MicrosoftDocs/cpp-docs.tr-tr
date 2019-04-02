---
title: Derleyici Uyarısı C4958
ms.date: 11/04/2016
f1_keywords:
- C4958
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
ms.openlocfilehash: 96b73975f391493340dd01d85ad30a8c888b44c0
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769413"
---
# <a name="compiler-warning-c4958"></a>Derleyici Uyarısı C4958

> '*işlemi*': işaretçi aritmetik doğrulanabilir değil

## <a name="remarks"></a>Açıklamalar

İşaretçi aritmetiği kullanma, doğrulanamayan bir görüntü oluşturur.

Daha fazla bilgi için [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Bu uyarı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnekte C4958 oluşturur:

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

Derleyicinin dizi işaretçi aritmetik işlemlerle uygular. Bu nedenle, yerel dizi doğrulanabilir değildir; CLR dizisi kullanın. Daha fazla bilgi için [dizi](../../extensions/arrays-cpp-component-extensions.md).

Aşağıdaki örnekte C4958 oluşturur:

```cpp
// C4958b.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )

int main() {
   int array[5];
   array[4] = 0;   // C4958
}
```