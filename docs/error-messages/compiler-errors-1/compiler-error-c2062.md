---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2062'
title: Derleyici hatası C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: ef477fba9bb1208076dd6969cb78b7495d5536e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328649"
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
