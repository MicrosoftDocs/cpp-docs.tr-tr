---
title: Derleyici Uyarısı (düzey 1) C4807
ms.date: 11/04/2016
f1_keywords:
- C4807
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
ms.openlocfilehash: 2424d076be0914a68c3227566cb851b7ab64cc0f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175044"
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
