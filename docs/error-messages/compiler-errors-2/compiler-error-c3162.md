---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3162'
title: Derleyici hatası C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: ca44b27607a34a469a5fd6fc1371e1510452247a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242320"
---
# <a name="compiler-error-c3162"></a>Derleyici hatası C3162

' Type ': yok edicisi olan bir başvuru türü statik veri üyesi ' Member ' türü olarak kullanılamaz

Ortak dil çalışma zamanı, sınıf de statik üye işlevi içerdiğinde Kullanıcı tanımlı yıkıcının ne zaman çalıştırılacağını bilmiyor.

Nesne açıkça silinmediği takdirde yıkıcı hiçbir şekilde çalışmaz.

Daha fazla bilgi için bkz.,

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek C3162 oluşturur.

```cpp
// C3162.cpp
// compile with: /clr /c
ref struct A {
   ~A() { System::Console::WriteLine("in destructor"); }
   static A i;   // C3162
   static A^ a = gcnew A;   // OK
};

int main() {
   A ^ a = gcnew A;
   delete a;
}
```
