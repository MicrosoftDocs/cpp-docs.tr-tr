---
title: Derleyici hatası C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: a709a540b24756a7e08f98552c5888a55c3ea601
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735976"
---
# <a name="compiler-error-c2062"></a>Derleyici hatası C2062

' Type ' türü beklenmiyor

Derleyici bir tür adı beklememedi.

Aşağıdaki örnek C2062 oluşturur:

```cpp
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062, derleyicinin parametre listesinde tanımsız türleri işleme yöntemi nedeniyle de oluşabilir. Derleyici tanımsız (yanlış yazılmış?) türle karşılaşırsa, oluşturucunun bir ifade olduğunu varsayar ve C2062 yayınlar. Çözümlemek için, yalnızca bir oluşturucu parametre listesinde tanımlı türleri kullanın.
