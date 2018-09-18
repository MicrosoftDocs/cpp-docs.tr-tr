---
title: Derleyici Hatası C3073 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3073
dev_langs:
- C++
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a46553530d8aaebaf44a71a41203764695b1868d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050807"
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