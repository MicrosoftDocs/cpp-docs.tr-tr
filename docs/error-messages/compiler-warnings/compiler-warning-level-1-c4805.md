---
title: Derleyici Uyarısı (düzey 1) C4805
ms.date: 11/04/2016
f1_keywords:
- C4805
helpviewer_keywords:
- C4805
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
ms.openlocfilehash: 129bff79b35fb14136cbf8127a3cfb77fc0d2a40
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051299"
---
# <a name="compiler-warning-level-1-c4805"></a>Derleyici Uyarısı (düzey 1) C4805

' Operation ': işlem içinde ' Type ' türü ve ' Type ' türü güvenli olmayan karışımı

Bu uyarı [bool](../../cpp/bool-cpp.md) ve [int](../../c-language/integer-types.md)arasındaki karşılaştırma işlemleri için oluşturulur. Aşağıdaki örnek C4805 oluşturur:

```cpp
// C4805.cpp
// compile with: /W1
int main() {
   int i = 1;
   bool b = true;

   if (i == b) {   // C4805, comparing bool and int variables
   }
}
```