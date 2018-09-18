---
title: Derleyici Hatası C2761 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2761
dev_langs:
- C++
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2083f08ad79a9fd53148e7c166ec276a9ddf4cde
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075247"
---
# <a name="compiler-error-c2761"></a>Derleyici Hatası C2761

'function': üye işlev yeniden bildirimi izin verilmiyor

Üye işlevini yeniden bildirilemiyor. Tanımlayabilirsiniz, ancak yeniden bildirmek değil.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2761 oluşturur.

```
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761

```

## <a name="example"></a>Örnek

Statik olmayan üye bir sınıfın veya yapının tanımlanamaz.  Aşağıdaki örnek, C2761 oluşturur.

```
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```