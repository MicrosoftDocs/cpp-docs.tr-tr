---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4212'
title: Derleyici Uyarısı (düzey 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: 3c557e5fa11e2a6fb1f15e5389901ede537755af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297362"
---
# <a name="compiler-warning-level-4-c4212"></a>Derleyici Uyarısı (düzey 4) C4212

Standart olmayan uzantı kullanıldı: işlev bildirimi kullanılan üç nokta

İşlev prototipi değişken sayıda bağımsız değişkene sahiptir. İşlev tanımı değil.

Aşağıdaki örnek C4212 oluşturur:

```c
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```
