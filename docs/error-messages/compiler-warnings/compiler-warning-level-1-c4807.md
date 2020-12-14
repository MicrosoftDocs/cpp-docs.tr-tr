---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4807'
title: Derleyici Uyarısı (düzey 1) C4807
ms.date: 11/04/2016
f1_keywords:
- C4807
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
ms.openlocfilehash: 4c015d2ee7c566199411374402719c4a8eaee37f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238147"
---
# <a name="compiler-warning-level-1-c4807"></a>Derleyici Uyarısı (düzey 1) C4807

' işlem ': ' Type ' türü ve ' Type ' türünde imzalı bit alanından güvenli olmayan karışımı

Bu uyarı, tek bitlik imzalı bir bit alanı bir değişkenle karşılaştırılırken oluşturulur **`bool`** . Tek bit, işaretli bir bit alanı yalnızca-1 veya 0 değerlerini içerebildiğinden, bunu ile karşılaştırmak tehlikelidir **`bool`** . Karıştırma **`bool`** ve tek bit, işaretsiz bitalanlar hakkında, ile özdeş olduğundan **`bool`** ve yalnızca 0 veya 1 tutabilecek bir uyarı oluşturulmaz.

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
