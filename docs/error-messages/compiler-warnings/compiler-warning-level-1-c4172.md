---
title: Derleyici Uyarısı (düzey 1) C4172 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4172
dev_langs:
- C++
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56f606b48fb060472dd67d34800c06946bc41712
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043514"
---
# <a name="compiler-warning-level-1-c4172"></a>Derleyici Uyarısı (düzey 1) C4172

yerel değişkenin veya geçici adresini döndürüyor

Bir işlev bir yerel değişken veya geçici nesnenin adresini döndürür. Bir işlev geri döndüğünde, döndürülen adresi geçerli değil. Bu nedenle yerel değişkenleri ve geçici nesneler yok edilir.

İşlevi, yerel bir nesnenin adresini döndürmeyen olacak şekilde yeniden tasarlayın.

Aşağıdaki örnek, C4172 oluşturur:

```
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```