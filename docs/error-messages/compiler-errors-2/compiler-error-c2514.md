---
title: Derleyici Hatası C2514 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2514
dev_langs:
- C++
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 392c46224078c35df5ae02a88503726b193c87f3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085517"
---
# <a name="compiler-error-c2514"></a>Derleyici Hatası C2514

'class': sınıfın hiç oluşturucusu yok

Sınıf, yapı veya birleşim örneğini başlatmak için kullanılan parametrelerle eşleşen bir parametre listesi ile hiçbir oluşturucu vardır.

Bir sınıf örneği önce tam olarak bildirilmelidir.

Aşağıdaki örnek, C2514 oluşturur:

```
// C2514.cpp
// compile with: /c
class f;

class g {
public:
    g (int x);
};

class fmaker {
   f *func1() {
      return new f(2);   // C2514
   }

   g *func2() {
      return new g(2);   // OK
   }
};
```