---
title: Derleyici Uyarısı C4957
ms.date: 11/04/2016
f1_keywords:
- C4957
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
ms.openlocfilehash: ada10b5989b714ec4c75a24de1bbb101e1f51ee6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230772"
---
# <a name="compiler-warning-c4957"></a>Derleyici Uyarısı C4957

> '*cast*': '*cast_from*' öğesinden '*cast_to*' öğesine açık atama doğrulanabilir değil

## <a name="remarks"></a>Açıklamalar

Bir atama doğrulanamayan bir görüntüye neden olur.

Bazı atamalar güvenlidir (örneğin, **`static_cast`** Kullanıcı tanımlı dönüştürmeleri ve a 'yı tetikleyen bir **`const_cast`** ). Doğrulanabilir kod oluşturmak için bir [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) garanti edilir.

Daha fazla bilgi için bkz. [saf ve Doğrulanabilen kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/Clr: Safe** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Bu uyarı bir hata olarak verilir ve [Uyarı](../../preprocessor/warning.md) pragması veya [/WD](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği ile devre dışı bırakılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4957 oluşturur:

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
