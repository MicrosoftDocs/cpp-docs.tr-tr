---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3309'
title: Derleyici hatası C3309
ms.date: 11/04/2016
f1_keywords:
- C3309
helpviewer_keywords:
- C3309
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
ms.openlocfilehash: e18f306b58cf4c5480d32305f6dcc8c9070a8768
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337378"
---
# <a name="compiler-error-c3309"></a>Derleyici hatası C3309

' macro_name ': modül adı bir makro veya anahtar sözcük olamaz

Modül özniteliğinin Name özelliğine geçirdiğiniz değer Önişlemci 'nin genişlemesine yönelik bir sembol olamaz; bir dize sabit değeri olmalıdır.

Aşağıdaki örnek C3309 oluşturur:

```cpp
// C3309.cpp
#define NAME MyModule
[module(name="NAME")];   // C3309
// Try the following line instead
// [module(name="MyModule")];
[coclass]
class MyClass {
public:
   void MyFunc();
};

int main() {
}
```
