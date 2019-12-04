---
title: Derleyici hatası C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: 95cd2c4af614906da7ba2d1c4c5dd488059f970a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761809"
---
# <a name="compiler-error-c3162"></a>Derleyici hatası C3162

' Type ': yok edicisi olan bir başvuru türü statik veri üyesi ' Member ' türü olarak kullanılamaz

Ortak dil çalışma zamanı, sınıf de statik üye işlevi içerdiğinde Kullanıcı tanımlı yıkıcının ne zaman çalıştırılacağını bilmiyor.

Nesne açıkça silinmediği takdirde yıkıcı hiçbir şekilde çalışmaz.

Daha fazla bilgi için bkz.,

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

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
