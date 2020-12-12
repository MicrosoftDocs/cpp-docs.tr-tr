---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3073'
title: Derleyici hatası C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: e26938d6c708c364bb2447b793abf7d51adb5779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320253"
---
# <a name="compiler-error-c3073"></a>Derleyici hatası C3073

' Type ': başvuru sınıfının Kullanıcı tanımlı bir kopya Oluşturucusu yok

[/Clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) derlemesinde, derleyici bir başvuru türü için bir kopya Oluşturucu oluşturmaz. Herhangi bir **/clr** derlemesinde, bir tür örneğinin kopyalanmasını beklediğinizi bir başvuru türü için kendi kopya oluşturucuyu tanımlamanız gerekir.

Daha fazla bilgi için bkz. [başvuru türleri için C++ yığın semantiği](../../dotnet/cpp-stack-semantics-for-reference-types.md).

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
