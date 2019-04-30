---
title: Derleyici Uyarısı C4957
ms.date: 11/04/2016
f1_keywords:
- C4957
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
ms.openlocfilehash: 79a1b516db1508c755693b67ca2e4070095839da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388676"
---
# <a name="compiler-warning-c4957"></a>Derleyici Uyarısı C4957

> '*atama*': açık tür dönüştürme gelen '*cast_from*'to'*cast_to*' doğrulanabilir değil

## <a name="remarks"></a>Açıklamalar

Bir yayın doğrulanamayan bir görüntüde neden olur.

Bazı yayınları güvenlidir (örneğin, bir `static_cast` , kullanıcı tanımlı dönüşümler tetikler ve `const_cast`). A [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) doğrulanabilen kod üretmek için sağlanır.

Daha fazla bilgi için [saf ve doğrulanabilen kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Bu uyarı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4957 oluşturur:

```cpp
// C4957.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4957 )
using namespace System;
int main() {
   Object ^ o = "Hello, World!";
   String ^ s = static_cast<String^>(o);   // C4957
   String ^ s2 = safe_cast<String^>(o);   // OK
}
```