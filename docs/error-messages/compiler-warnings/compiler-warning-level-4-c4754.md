---
title: "Derleyici Uyarısı (düzey 4) C4754 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4754
dev_langs:
- C++
helpviewer_keywords:
- C4754
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae6bad6452e1d119659c8588531c82671d031863
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4754"></a>Derleyici Uyarısı (düzey 4) C4754
Bir karşılaştırma aritmetik işlemler için dönüştürme kurallarını, tek şube yürütülemez anlamına gelir.  
  
 Karşılaştırmanın sonucu her zaman aynı olduğundan C4754 uyarı görüntülenir. Bu, ilişkili tamsayı ifade yanlış olduğundan koşul dalları birini hiçbir zaman, büyük olasılıkla yerine getirildiğini gösterir. Bu kod hatası genellikle 64-bit mimariyi üzerinde yanlış tamsayı taşma denetimleri gerçekleşir.  
  
 Tamsayı dönüştürme kurallarını karmaşıktır ve çoğu Zarif Tuzaklar vardır. Her C4754 uyarı düzelttikten alternatif olarak, kullanılacak kodu güncelleştirebilirsiniz [SafeInt Kitaplığı](../../windows/safeint-library.md).  
  
## <a name="example"></a>Örnek  
 Bu örnek C4754 oluşturur:  
  
```cpp  
// C4754a.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int sum_overflow(unsigned long a, unsigned long b)   
{  
   unsigned long long x = a + b; // C4754  
  
   if (x > 0xFFFFFFFF)   
   {  
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 Ek `a + b` sonucu bir 64-bit değerine başvurmanıza önce aritmetik taşma neden olabilir ve 64-bit değişkenine atanan `x`. Bu onay üzerinde anlamına `x` artık kullanılmamaktadır ve hiçbir zaman catch taşma olur. Bu durumda, derleyici, bu uyarıyı gösterir:  
  
```Output  
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754a.cpp (7) mean that one branch cannot be executed. Cast '(a + ...)' to 'ULONG64' (or similar type of 8 bytes).  
```  
  
 Uyarı ortadan kaldırmak için 8-bayt değerleri için işlenen yayınlanamıyor atama deyimi değiştirebilirsiniz:  
  
```cpp  
// Casting one operand is sufficient to force all the operands in   
// the addition be upcast according to C/C++ conversion rules, but  
// casting both is clearer.  
unsigned long long x =   
   (unsigned long long)a + (unsigned long long)b;  
```  
  
## <a name="example"></a>Örnek  
 Sonraki örnek de C4754 oluşturur.  
  
```cpp  
// C4754b.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int wrap_overflow(unsigned long a)   
{  
   if (a + sizeof(unsigned long) < a) // C4754  
   {   
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 `sizeof()` İşleci döndüren bir `size_t`, büyüklüğü mimari bağımlı. Örnek kod, 32-bit mimariler çalışır burada bir `size_t` bir 32 bit türüdür. Ancak, 64 bit mimariyi üzerinde `size_t` bir 64-bit türüdür. Tamsayılara dönüştürme kurallarını anlama `a` ifadesinde bir 64-bit değerine başvurmanıza olan `a + b < a` gibi yazılmışsa `(size_t)a + (size_t)b < (size_t)a`. Zaman `a` ve `b` 32 bit tamsayı olduğunu, 64-bit ek işlemi hiçbir zaman taşabilir ve kısıtlama hiç tutar. Sonuç olarak, kodu, hiçbir zaman bir 64-bit mimariyi tamsayı taşma koşula algılar. Bu örnekte, bu uyarıyı yaymak üzere derleyici neden olur:  
  
```Output  
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754b.cpp (7) mean that one branch cannot be executed. Cast '4' to 'ULONG' (or similar type of 4 bytes).  
```  
  
 Bildirim uyarı iletisi açıkça yerine özgün kaynak dize sabit değeri 4 listeler — zamanına göre uyarı çözümleme soruna neden olan kod karşılaştığında `sizeof(unsigned long)` zaten bir sabite dönüştürüldü. Bu nedenle, izlemek hangi kaynak ifadesinde kod uyarı iletisi sabit değer ile ilişkili çalışmıyor olabilir. C4754 uyarı iletilerini sabitler çözümlendi kodunun en yaygın kaynakları gibi ifadelerini `sizeof(TYPE)` ve `strlen(szConstantString)`.  
  
 Bu durumda, sabit kod bu benzeyecektir:  
  
```cpp  
// Casting the result of sizeof() to unsigned long ensures  
// that all the addition operands are 32-bit, so any overflow   
// is detected by the check.  
if (a + (unsigned long)sizeof(unsigned long) < a)  
  
```  
  
 **Not** derleyici uyarıları başvurulan satır numarası son bir deyim satırıdır. Birden çok hatları üzerinden yayılan karmaşık bir koşul deyimi hakkında bir uyarı iletisinde bildirilen satırından önce birkaç satır kod hatası olan satır olabilir. Örneğin:  
  
```cpp  
unsigned long a;  
  
if (a + sizeof(unsigned long) < a || // incorrect check  
    condition1() ||   
    a == 0) {    // C4754 warning reported on this line  
         // never executes!  
         return INVALID_PARAMETER;  
}  
```