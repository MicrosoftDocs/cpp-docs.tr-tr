---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2516'
title: Derleyici hatası C2516
ms.date: 11/04/2016
f1_keywords:
- C2516
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
ms.openlocfilehash: 1561a6917d26a9cc4c71a8970e7a75512c1a1b61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339291"
---
# <a name="compiler-error-c2516"></a>Derleyici hatası C2516

' name ': geçerli bir taban sınıf değil

Sınıfı, bir ifadesiyle tanımlanan bir tür adından türetilir **`typedef`** .

Aşağıdaki örnek C2516 oluşturur:

```cpp
// C2516.cpp
typedef unsigned long ulong;
class C : public ulong {}; // C2516
```
