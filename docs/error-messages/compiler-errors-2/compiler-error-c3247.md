---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3247'
title: Derleyici hatası C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 02e8f20f9804067e0179f3b5583d589d16dae302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307202"
---
# <a name="compiler-error-c3247"></a>Derleyici hatası C3247

' Class1 ': bir coclass başka bir ' Class2 ' coclass 'ından devralınabilir

[Coclass](../../windows/attributes/coclass.md) özniteliğiyle işaretlenmiş bir sınıf, özniteliğiyle işaretlenmiş başka bir sınıftan devralınabilir `coclass` .

Aşağıdaki örnek C3247 oluşturur:

```cpp
// C3247.cpp
[module(name="MyLib")];
[coclass]
class a {
};

[coclass]
class b : public a {   // C3247
};
int main() {
}
```
