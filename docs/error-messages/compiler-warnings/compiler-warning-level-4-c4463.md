---
title: "Derleyici Uyarısı (düzey 4) C4463 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4463
dev_langs: C++
helpviewer_keywords: C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71b438de515a4fd01e7714de685ee0a89adb609e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4463"></a>Derleyici Uyarısı (düzey 4) C4463  
  
> taşma; atama *değeri* değerleri yalnızca tutabileceği bit alanına *low_value* için *high_value*  
  
Atanan *değeri* bit alanın içerebileceği değerleri aralığı dışında. İmzalı bit alanı türlerini kullanan oturum için bit yüksek düzey dolayısıyla  *n*  imzalı bit alanları için -2 bit alanı aralığı boyutudur<sup>n-1</sup> 2<sup>n-1</sup>-1, sırada bit alanları imzasız bir aralığınız 0'dan 2<sup>n</sup>-1.  
  
## <a name="example"></a>Örnek  
  
Bu örnek, C4463 oluşturur, bit-türünde bir alan için bir değer 3'ün atamaya çalıştığı `int` 2 boyuta sahip olan 1 -2 arasında bir aralık.  
  
Bu sorunu gidermek için izin verilen aralıktaki bir şey için atanan değeri değiştirebilirsiniz. Bit alanı imzasız değerler 0 ile 3 aralığında tutmak için amaçlanıyorsa bildirim türünü değiştirebilirsiniz `unsigned`. Alan değerleri aralığı -4 için 3'te tutmak üzere tasarlanmıştır, 3'e bit alan boyutunu değiştirebilirsiniz.  
  
```cpp  
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S { 
    int x : 2; // int type treats high-order bit as sign
}; 

int main() { 
    S s; 
    s.x = 3; // warning C4463: overflow; assigning 3 
    // to bit-field that can only hold values from -2 to 1 
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type 
    // to unsigned.
} 
```  
