---
title: Derleyici Hatası C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 7ca84b4f054852aefa75a9c4547286137b436c63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182489"
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