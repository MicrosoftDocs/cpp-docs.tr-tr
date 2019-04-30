---
title: Derleyici Hatası C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: dcfac9629a90b82744f87ec105c30301b2102cdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408751"
---
# <a name="compiler-error-c2062"></a>Derleyici Hatası C2062

türü 'type' beklenmeyen

Derleyici, bir tür adı beklenmiyordu.

Aşağıdaki örnek, C2062 oluşturur:

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 tanıtıcıları tanımlanmamış bir oluşturucunun parametre listesi türlerinde derleyici yöntemi nedeniyle ortaya çıkabilir. Derleyici tanımlanmamış bir (yazılmış?) türü karşılaşırsa, oluşturucu bir ifade ve C2062 sorunları varsayar. Çözümlemek için yalnızca bir oluşturucu parametre listesinde tanımlı türleri kullanın.