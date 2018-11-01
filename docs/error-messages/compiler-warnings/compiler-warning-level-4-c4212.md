---
title: Derleyici Uyarısı (düzey 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: 8eca942de1d2f78f5e42d4aac7e2441789a01862
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598906"
---
# <a name="compiler-warning-level-4-c4212"></a>Derleyici Uyarısı (düzey 4) C4212

Standart olmayan uzantı kullanıldı: işlev bildirimi üç nokta kullanılan

İşlev prototipi değişken sayıda bağımsız değişken var. İşlev tanımı izin vermez.

Aşağıdaki örnek, C4212 oluşturur:

```
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```