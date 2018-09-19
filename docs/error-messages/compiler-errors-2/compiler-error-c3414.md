---
title: Derleyici Hatası C3414 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3414
dev_langs:
- C++
helpviewer_keywords:
- C3414
ms.assetid: 715f5432-b509-4f8f-84f5-e1463bac490f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c07033489538011889ef939599b30b88664c08ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135773"
---
# <a name="compiler-error-c3414"></a>Derleyici Hatası C3414

'member': içeri aktarılan üye işlev tanımlanamıyor

Kodda başvurulan bir derlemede tanımlanmış bir üye tanımlandı.

Aşağıdaki örnek, C3414 oluşturur:

```
// C3414a2.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

ve ardından:

```
// C3414b2.cpp
// compile with: /clr
#using <C3414a2.dll>

void MyClass::Test() {    // C3414
}

System::Object::Object() {    // C3414
}
```
