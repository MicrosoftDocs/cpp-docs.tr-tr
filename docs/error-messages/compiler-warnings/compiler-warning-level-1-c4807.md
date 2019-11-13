---
title: Derleyici Uyarısı (düzey 1) C4807
ms.date: 11/04/2016
f1_keywords:
- C4807
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
ms.openlocfilehash: c18dbac0681067d9bc52455dfdbe44a24c786ee7
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051539"
---
# <a name="compiler-warning-level-1-c4807"></a>Derleyici Uyarısı (düzey 1) C4807

' işlem ': ' Type ' türü ve ' Type ' türünde imzalı bit alanından güvenli olmayan karışımı

Bu uyarı, tek bitlik imzalı bir bit alanı `bool` değişkeniyle karşılaştırılırken oluşturulur. Tek bit, işaretli bir bit alanı yalnızca-1 veya 0 değerlerini içerebildiğinden, `bool`karşılaştırmak tehlikelidir. `bool` özdeş olduklarından ve yalnızca 0 veya 1 ' i tutabileceğinden, `bool` ve tek bit, işaretsiz bitalanları karıştırma hakkında hiçbir uyarı oluşturulmaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4807 oluşturur:

```cpp
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