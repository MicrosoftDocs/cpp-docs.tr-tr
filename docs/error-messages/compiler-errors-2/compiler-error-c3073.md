---
title: Derleyici Hatası C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: 8a4a2011124056af7064c8241450e1f3613776a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580875"
---
# <a name="compiler-error-c3073"></a>Derleyici Hatası C3073

'type': başvuru sınıfının kullanıcı tanımlı kopya oluşturucu yok

İçinde bir [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) derleme, derleyici bir başvuru türü için bir kopya Oluşturucu oluşturmaz. Herhangi **/CLR** derleme tanımlamalısınız kendi kopya oluşturucusu için bir başvuru türü kopyalanacak türünün bir örneği bekliyorsanız.

Daha fazla bilgi için [başvuru türleri için C++ yığın anlamları](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3073 oluşturur.

```
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