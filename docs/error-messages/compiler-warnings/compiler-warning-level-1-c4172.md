---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4172'
title: Derleyici Uyarısı (düzey 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: 7bcfe460150e543c1e3fb6a93ed6656619b5cb13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266942"
---
# <a name="compiler-warning-level-1-c4172"></a>Derleyici Uyarısı (düzey 1) C4172

yerel değişkenin veya geçici adresin adresi döndürülüyor

Bir işlev, yerel bir değişkenin veya geçici nesnenin adresini döndürür. Bir işlev döndürüldüğünde yerel değişkenler ve geçici nesneler yok edilir, bu nedenle döndürülen adres geçerli değildir.

İşlevi bir yerel nesnenin adresini döndürmemesi için yeniden tasarlayabilmenizi öneririz.

Aşağıdaki örnek C4172 oluşturur:

```cpp
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```
