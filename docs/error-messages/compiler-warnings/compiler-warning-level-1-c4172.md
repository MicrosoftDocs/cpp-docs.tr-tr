---
title: Derleyici Uyarısı (düzey 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: 7d53972dbcb2e3ab6a95b0b874cc6bb98cd66840
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624820"
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