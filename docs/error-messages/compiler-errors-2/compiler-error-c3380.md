---
title: Derleyici hatası C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: 2e26b4b1af8ee3c078f3eae3c0cb6a2677c642c2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761887"
---
# <a name="compiler-error-c3380"></a>Derleyici hatası C3380

' class ': geçersiz derleme erişim belirticisi-yalnızca ' Public ' veya ' Private ' kullanılabilir

Yönetilen bir sınıfa veya yapıya uygulandığında, [ortak](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükler, sınıfın derleme meta verileri aracılığıyla gösterilip gösterilmeyeceğini belirtir. [/Clr](../../build/reference/clr-common-language-runtime-compilation.md)ile derlenen programdaki bir sınıfa yalnızca `public` veya `private` uygulanabilir.

`ref` ve `value` anahtar sözcükleri [/clr](../../build/reference/clr-common-language-runtime-compilation.md)ile kullanıldığında bir sınıfın yönetildiğini belirtir (bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Aşağıdaki örnek C3380 oluşturur:

```cpp
// C3380_2.cpp
// compile with: /clr
protected ref class A {   // C3380
// try the following line instead
// ref class A {
public:
   static int i = 9;
};

int main() {
   A^ myA = gcnew A;
   System::Console::WriteLine(myA->i);
}
```
