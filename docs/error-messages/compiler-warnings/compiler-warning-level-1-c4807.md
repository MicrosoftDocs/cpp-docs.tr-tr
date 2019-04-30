---
title: Derleyici Uyarısı (düzey 1) C4807
ms.date: 11/04/2016
f1_keywords:
- C4807
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
ms.openlocfilehash: a68596136e61aa33176365a4eff818124463b77e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390470"
---
# <a name="compiler-warning-level-1-c4807"></a>Derleyici Uyarısı (düzey 1) C4807

'operation': Güvenli olmayan karışımı türü 'type' ve type 'türü imzalı bit alanından mantıksal karşılaştırmaya

Bu uyarı için bir bit imzalı bit alanı karşılaştırılırken oluşturulan bir `bool` değişkeni. Bir bit, imzalı bit alanı yalnızca değerleri -1 veya 0 içerebileceğinden, kendisine Karşılaştırılacak tehlikeli `bool`. Karıştırma hakkında uyarı oluşturulan `bool` ve aynı olduğundan bir bit, işaretsiz bit alanları `bool` ve yalnızca 0 veya 1 içerebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4807 oluşturur:

```
// C4807.cpp
// compile with: /W1
typedef struct bitfield {
   signed mybit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bool b = true;

   // try..
   // int b = true;

   bf.mybit = -1;
   if (b == bf.mybit) {   // C4807
      b = false;
   }
}
```