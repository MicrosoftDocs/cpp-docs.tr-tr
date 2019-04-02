---
title: Derleyici Hatası C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: 516690f2524d48e7abbf7546592c6346e92c3e2e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781607"
---
# <a name="compiler-error-c3380"></a>Derleyici Hatası C3380

'class': Geçersiz derleme erişim belirticisi - yalnızca 'public' veya 'private' kullanılabilir

Bir yönetilen sınıf veya yapının uygulandığında [genel](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükleri sınıfı derleme meta verileri kullanıma sunulacak olup olmadığını gösterir. Yalnızca `public` veya `private` ile derlenmiş bir program içerisinde bir sınıf uygulanabilir [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

`ref` Ve `value` anahtar sözcükleri ile kullanıldığında, [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), bir sınıf yönetildiğini belirtmek (bkz [sınıfları ve yapıları](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Aşağıdaki örnek, C3380 oluşturur:

```
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
