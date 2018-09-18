---
title: Derleyici Hatası C3380 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e35c4edaf24aacbd7eb9938a1dea2c470d32caae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062598"
---
# <a name="compiler-error-c3380"></a>Derleyici Hatası C3380

'class': Geçersiz derleme erişim belirticisi - yalnızca 'public' veya 'private' kullanılabilir

Bir yönetilen sınıf veya yapının uygulandığında [genel](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükleri sınıfı derleme meta verileri kullanıma sunulacak olup olmadığını gösterir. Yalnızca `public` veya `private` ile derlenmiş bir program içerisinde bir sınıf uygulanabilir [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

`ref` Ve `value` anahtar sözcükleri ile kullanıldığında, [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), bir sınıf yönetildiğini belirtmek (bkz [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md)).

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
