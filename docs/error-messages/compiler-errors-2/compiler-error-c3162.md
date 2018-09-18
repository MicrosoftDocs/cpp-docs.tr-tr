---
title: Derleyici Hatası C3162 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3162
dev_langs:
- C++
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 529dfa41064e9d22b796b9d079a67b213b816fb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030943"
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