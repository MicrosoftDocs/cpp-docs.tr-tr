---
title: Bir özel durum filtresi yazma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb9307b68b5d664e477f0139824ff02d00b7c134
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462124"
---
# <a name="writing-an-exception-filter"></a>Özel Durum Filtresi Yazma
Özel bir durumu, özel durum işleyicisinin düzeyine atlayarak veya yürütmeyi devam ettirerek işleyebilirsiniz. Kullanabileceğiniz özel durum ve başarısız işlemler için özel durum işleyicisi kodunu kullanmak yerine, *filtre* sorunu ve ardından, -1 döndürerek, normal akışa yığını temizlemeden sürdürmek için.  
  
> [!NOTE]
>  Bazı özel durumlar devam ettirilemez. Varsa *filtre* değerlendirir böyle bir özel durum için -1 için sistem yeni bir özel durum oluşturur. Çağırdığınızda [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552), özel durumun devam edip etmeyeceğini siz belirlersiniz.  
  
 Örneğin, aşağıdaki kod bir işlev çağrısı kullanır *filtre* ifade: Bu işlev sorunu giderir ve normal denetim akışını sürdürmek için -1 döndürür:  
  
```cpp 
// exceptions_Writing_an_Exception_Filter.cpp  
#include <windows.h>  
int main() {  
   int Eval_Exception( int );  
  
   __try {}  
  
   __except ( Eval_Exception( GetExceptionCode( ))) {  
      ;  
   }  
  
}  
void ResetVars( int ) {}  
int Eval_Exception ( int n_except ) {  
   if ( n_except != STATUS_INTEGER_OVERFLOW &&   
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions  
   return EXCEPTION_CONTINUE_SEARCH;  
  
   // Execute some code to clean up problem  
   ResetVars( 0 );   // initializes data to 0  
   return EXCEPTION_CONTINUE_EXECUTION;  
}  
```  
  
 Bir işlev çağrısı kullanmak iyi bir fikirdir *filtre* ifadesi her *filtre* karmaşık bir şey yapmanız gerekir. İfadenin değerlendirilmesi işlevin, bu durumda `Eval_Exception`'ın yürütülmesine neden olur.  
  
 Kullanımına dikkat edin [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) özel durumu belirlemek için. Filtrenin içinde bu işlevi çağırmanız gerekir. `Eval_Exception` çağrılamıyor `GetExceptionCode`, ancak geçirilen özel durum kodu olması gerekir.  
  
 Bu işleyici, özel durum bir tamsayı veya kayan nokta taşması değilse deneyimi başka bir işleyiciye geçirir. Tamsayı veya kayan nokta taşmasıysa, işleyici bazı genel değişkenleri sıfırlamak için bir işlev çağırır (`ResetVars` yalnızca bir örnektir, API işlevi değildir). *Deyim bloğu 2*, bu örnekte boş, hiçbir zaman yürütülebilir olduğundan `Eval_Exception` hiçbir zaman exceptıon_execute_handler (1) döndürür.  
  
 Bir işlev çağrısı kullanmak, karmaşık filtre ifadeleriyle başa çıkmak için genel anlamda iyi bir yöntemdir. Yararlı olan diğer iki C dili özelliği şunlardır:  
  
-   Koşullu işleç  
  
-   Virgül işleci  
  
 Koşullu işleç, belirli bir dönüş kodunu denetlemek ve ardından iki farklı değerden birini döndürmek için kullanılabildiğinden genellikle çok yararlı olur. Örneğin, yalnızca özel durum STATUS_INTEGER_OVERFLOW ise özel durum filtresi aşağıdaki kodda tanır:  
  
```cpp 
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 Bu durumda koşullu işlecin amacı, temel olarak netlik sağlamaktır, çünkü aşağıdaki kod aynı sonuçları oluşturur:  
  
```cpp 
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 Koşullu işleç, -1, exceptıon_contınue_executıon değerlendirmek için filtreyi isteyebileceğiniz durumlarda daha yararlı olur.  
  
 Virgül işleci, tek bir ifade içerisinde birden fazla bağımsız işlemler gerçekleştirmenizi sağlar. Etkisi, kabaca birden fazla deyim yürütmeye ve ardından son ifadenin değerini döndürmeye benzerdir. Örneğin, aşağıdaki kod özel durum kodunu bir değişkende depolar ve ardından bunu test eder:  
  
```cpp 
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)