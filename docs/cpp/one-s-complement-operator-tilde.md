---
title: "Bir &#39; s tamamlama işleci: ~ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ~
dev_langs: C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 635a3e3b2d270d2164adc3f25a260085d7c50d60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="one39s-complement-operator-"></a>Bir &#39; s tamamlama işleci: ~
## <a name="syntax"></a>Sözdizimi  
  
```  
  
~ cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bazen "bit düzeyinde tamamlayıcı" işleci olarak anılan birinin tamamlayıcı işleci (`~`), bit düzeyinde birinin kendi işleneninin tamamlayıcısını oluşturur. Yani, işlenende 1 olan her bit sonuçta 0'dır. Buna karşılık, işlenende 0 olan her bit sonuçta 1'dir. Birinin tamamlayıcı işlecinin işleneni integral türünde olmalıdır.  
  
## <a name="operator-keyword-for-"></a>~ için İşleç Anahtar Sözcüğü  
 `compl` işleci, `~` öğesinin metin eşdeğeridir. Erişim için iki yolla `compl` programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="example"></a>Örnek  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 Bu örnekte, `y`'ye atanan yeni değer işaretsiz 0xFFFF değerinin veya 0x0000 için birinin tamamlayıcısıdır.  
  
 İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Bkz: [standart dönüşümler](standard-conversions.md) nasıl yükseltme yapılacağı hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Birli Aritmetik İşleçler](../c-language/unary-arithmetic-operators.md)