---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2055'
title: Derleyici hatası C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 0692488b8e1ea91fe235ade512c5fbe5094cdaef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174942"
---
# <a name="compiler-error-c2055"></a>Derleyici hatası C2055

tür listesi değil biçimsel parametre listesi bekleniyordu

Bir işlev tanımı, biçimsel parametre listesi yerine bir parametre türü listesi içerir. ANSI C, void veya üç nokta () olmadıkları müddetçe biçimsel parametrelerin adlandırılmaları gerekir `...` .

Aşağıdaki örnek C2055 oluşturur:

```c
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```
