---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2458'
title: Derleyici hatası C2458
ms.date: 11/04/2016
f1_keywords:
- C2458
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
ms.openlocfilehash: 7f705511c14da19b125868c1b34d907d6b5f220e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262860"
---
# <a name="compiler-error-c2458"></a>Derleyici hatası C2458

' tanımlayıcı ': tanım içinde yeniden tanımlama

Bir sınıf, yapı, birleşim veya numaralandırma kendi bildiriminde yeniden tanımlandı.

Aşağıdaki örnek C2458 oluşturur:

```cpp
// C2458.cpp
class C {
   enum i { C };   // C2458
};
```
