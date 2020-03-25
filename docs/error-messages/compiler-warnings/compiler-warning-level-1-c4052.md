---
title: Derleyici Uyarısı (düzey 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4052
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 0dcb6163a87a92f33e875dac8b200f414bb36be6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164137"
---
# <a name="compiler-warning-level-1-c4052"></a>Derleyici Uyarısı (düzey 1) C4052

işlev bildirimleri farklı; biri değişken bağımsız değişkenleri içerir

İşlevin bir bildirimi değişken bağımsız değişkenleri içermiyor. Yoksayılır.

Aşağıdaki örnek C4052 oluşturur:

```c
// C4052.c
// compile with: /W4 /c
int f();
int f(int i, ...);   // C4052
```
