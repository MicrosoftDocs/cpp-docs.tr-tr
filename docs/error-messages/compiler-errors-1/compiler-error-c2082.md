---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2082'
title: Derleyici hatası C2082
ms.date: 11/04/2016
f1_keywords:
- C2082
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
ms.openlocfilehash: 957699338d253ee2438060b27a0089a654fc4f9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316628"
---
# <a name="compiler-error-c2082"></a>Derleyici hatası C2082

' Identifier ' biçimsel parametresinin yeniden tanımlanması

İşleve biçimsel bir parametre, işlev gövdesi içinde yeniden bildirilmiştir. Hatayı gidermek için yeniden tanımı kaldırın.

Aşağıdaki örnek C2082 oluşturur:

```cpp
// C2082.cpp
void func(int i) {
   int i;   // C2082
   int ii;   // OK
}
```
