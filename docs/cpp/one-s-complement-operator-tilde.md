---
title: 'Bir&#39;s tamamlama işleci: ~ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- "~"
dev_langs:
- C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79d34a4057ccbe5c10a6d22a14eed4317e62c464
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408637"
---
# <a name="one39s-complement-operator-"></a>Bir&#39;s tamamlama işleci: ~
## <a name="syntax"></a>Sözdizimi  
  
```  
~ cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bazen "bit düzeyinde tamamlayıcı" işleci olarak anılan birinin tamamlayıcı işleci (`~`), bit düzeyinde birinin kendi işleneninin tamamlayıcısını oluşturur. Yani, işlenende 1 olan her bit sonuçta 0'dır. Buna karşılık, işlenende 0 olan her bit sonuçta 1'dir. Birinin tamamlayıcı işlecinin işleneni integral türünde olmalıdır.  
  
## <a name="operator-keyword-for-"></a>~ için İşleç Anahtar Sözcüğü  
 **Compl** işlecidir öğesinin metin eşdeğeridir `~`. Erişmenin iki yöntemi vardır **compl** programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
 İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Bkz: [standart dönüştürmeler](standard-conversions.md) yükseltmenin nasıl yapılacağı hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Birli Aritmetik İşleçler](../c-language/unary-arithmetic-operators.md)