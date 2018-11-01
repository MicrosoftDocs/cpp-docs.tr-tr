---
title: Derleyici Hatası C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 7ca84b4f054852aefa75a9c4547286137b436c63
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569175"
---
# <a name="compiler-error-c3247"></a>Derleyici Hatası C3247

'class1': bir coclass başka bir coclass 'class2' devralamaz

Bir sınıf ile işaretlenen [coclass'ı](../../windows/coclass.md) özniteliği ile işaretlenmiş başka bir sınıf'öğesinden özellik devralamaz `coclass` özniteliği.

Aşağıdaki örnek, C3247 oluşturur:

```
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