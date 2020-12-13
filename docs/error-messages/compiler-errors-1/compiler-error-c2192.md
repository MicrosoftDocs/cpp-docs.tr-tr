---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2192'
title: Derleyici hatası C2192
ms.date: 11/04/2016
f1_keywords:
- C2192
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
ms.openlocfilehash: 02b1b5ace60d2b9a288cf933a43c5603b734eac7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337683"
---
# <a name="compiler-error-c2192"></a>Derleyici hatası C2192

' number ' parametre bildirimi farklı

Bir C işlevi, farklı bir parametre listesi ile ikinci kez bildirildi. C, aşırı yüklenmiş işlevleri desteklemez.

Aşağıdaki örnek C2192 oluşturur:

```c
// C2192.c
// compile with: /Za /c
void func( float, int );
void func( int, float );   // C2192, different parameter list
void func2( int, float );   // OK
```
