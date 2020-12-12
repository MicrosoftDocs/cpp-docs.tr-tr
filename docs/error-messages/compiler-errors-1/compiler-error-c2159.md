---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2159'
title: Derleyici hatası C2159
ms.date: 11/04/2016
f1_keywords:
- C2159
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
ms.openlocfilehash: 045515ba964832de8821e048eac58b0ec507d830
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181221"
---
# <a name="compiler-error-c2159"></a>Derleyici hatası C2159

birden fazla depolama sınıfı belirtildi

Bir bildirimde birden fazla depolama sınıfı var.

Aşağıdaki örnek C2159 oluşturur:

```cpp
// C2159.cpp
// compile with: /c
static int i;   // OK
extern static int i;   // C2159
```
