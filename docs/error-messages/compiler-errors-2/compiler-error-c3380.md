---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3380'
title: Derleyici hatası C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: bb633d75d08fdbb902f086b3a4cd6a8a6db1fc69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334993"
---
# <a name="compiler-error-c3380"></a>Derleyici hatası C3380

' class ': geçersiz derleme erişim belirticisi-yalnızca ' Public ' veya ' Private ' kullanılabilir

Yönetilen bir sınıfa veya yapıya uygulandığında, [ortak](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükler, sınıfın derleme meta verileri aracılığıyla gösterilip gösterilmeyeceğini belirtir. Yalnızca `public` veya `private` [/clr](../../build/reference/clr-common-language-runtime-compilation.md)ile derlenen programdaki bir sınıfa uygulanabilir.

`ref`Ve `value` anahtar sözcükleri, [/clr](../../build/reference/clr-common-language-runtime-compilation.md)ile kullanıldığında bir sınıfın yönetildiğini belirtir (bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md)).

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
