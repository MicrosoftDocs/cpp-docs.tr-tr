---
title: Derleyici hatası C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: 0b53e704c14746579a32550726364c062a9ade6f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756753"
---
# <a name="compiler-error-c3073"></a>Derleyici hatası C3073

' Type ': başvuru sınıfının Kullanıcı tanımlı bir kopya Oluşturucusu yok

[/Clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) derlemesinde, derleyici bir başvuru türü için bir kopya Oluşturucu oluşturmaz. Herhangi bir **/clr** derlemesinde, bir tür örneğinin kopyalanmasını beklediğinizi bir başvuru türü için kendi kopya oluşturucuyu tanımlamanız gerekir.

Daha fazla bilgi için bkz [ C++ . başvuru türleri için yığın semantiği](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3073 oluşturur.

```cpp
// C3073.cpp
// compile with: /clr
ref class R {
public:
   R(int) {}
};

ref class S {
public:
   S(int) {}
   S(const S %rhs) {}   // copy constructor
};

void f(R) {}
void f2(S) {}
void f3(R%){}

int main() {
   R r(1);
   f(r);   // C3073
   f3(r);   // OK

   S s(1);
   f2(s);   // OK
}
```
