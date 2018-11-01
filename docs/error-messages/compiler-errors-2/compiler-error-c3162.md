---
title: Derleyici Hatası C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: f522a2de77e03a7c5f8f8dc774d62744417344fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540198"
---
# <a name="compiler-error-c3162"></a>Derleyici Hatası C3162

'type': bir yok Edicisi olan başvuru türü 'member' statik veri üyesinin türü kullanılamaz

Ortak dil çalışma zamanı sınıfı statik üye işlevini de içerdiğinde, kullanıcı tanımlı bir yok edici çalıştırmak ne zaman bilemezsiniz.

Nesneyi açıkça silinmedikçe bir yok edici hiç çalıştırılır.

Daha fazla bilgi için bkz:

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3162 oluşturur.

```
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