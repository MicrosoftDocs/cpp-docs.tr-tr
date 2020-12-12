---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2142'
title: Derleyici hatası C2142
ms.date: 11/04/2016
f1_keywords:
- C2142
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
ms.openlocfilehash: 65bd189fe99bb54549e458b093b72d8e47b840a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235534"
---
# <a name="compiler-error-c2142"></a>Derleyici hatası C2142

işlev bildirimleri farklı, değişken parametreleri yalnızca biri için belirtildi

İşlevin bir bildirimi bir değişken parametre listesi içerir. Başka bir bildirim değildir. Yalnızca ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)).

Aşağıdaki örnek C2142 oluşturur:

```c
// C2142.c
// compile with: /Za /c
void func();
void func( int, ... );   // C2142
void func2( int, ... );   // OK
```
