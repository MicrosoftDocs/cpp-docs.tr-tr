---
title: "Bir özel durum filtresi yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40afc6872ac04522c4c42f0a0d890b791ac03d53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-an-exception-filter"></a>Özel Durum Filtresi Yazma
Özel bir durumu, özel durum işleyicisinin düzeyine atlayarak veya yürütmeyi devam ettirerek işleyebilirsiniz. Kullanabileceğiniz özel durumu ve dönmeden işlemek için özel durum işleyici kodu kullanmak yerine, *filtre* sorunu giderip temizleyin ve ardından, -1 döndürerek normal akıştaki yığın silmeden sürdürmek için.  
  
> [!NOTE]
>  Bazı özel durumlar devam ettirilemez. Varsa *filtre* değerlendirir böyle bir özel durum için -1 olarak sistem yeni bir özel durum oluşturur. Çağırdığınızda [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552), özel durum sürdürecektir olup olmadığını belirler.  
  
 Örneğin, aşağıdaki kod bir işlev çağrısında kullanır *filtre* ifade: Bu işlev sorun işler ve denetimi normal akıştaki sürdürmek için -1 döndürür:  
  
```  
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
  
 Bir işlev çağrısında kullanmak iyi bir fikirdir *filtre* ifadesi her *filtre* karmaşık bir şey yapmanız gerekir. İfadenin değerlendirilmesi işlevin, bu durumda `Eval_Exception`'ın yürütülmesine neden olur.  
  
 Kullanımına dikkat edin [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) özel durumu belirlemek için. Filtrenin içinde bu işlevi çağırmanız gerekir. `Eval_Exception`çağrılamıyor **GetExceptionCode**, ancak kendisine geçirilen özel durum kodu olması gerekir.  
  
 Bu işleyici, özel durum bir tamsayı veya kayan nokta taşması değilse deneyimi başka bir işleyiciye geçirir. Tamsayı veya kayan nokta taşmasıysa, işleyici bazı genel değişkenleri sıfırlamak için bir işlev çağırır (`ResetVars` yalnızca bir örnektir, API işlevi değildir). *Deyimi bloğu 2*, bu örnekte boş olduğundan hiç yürütülebilir olduğundan `Eval_Exception` hiçbir zaman exceptıon_execute_handler (1) döndürür.  
  
 Bir işlev çağrısı kullanmak, karmaşık filtre ifadeleriyle başa çıkmak için genel anlamda iyi bir yöntemdir. Yararlı olan diğer iki C dili özelliği şunlardır:  
  
-   Koşullu işleç  
  
-   Virgül işleci  
  
 Koşullu işleç, belirli bir dönüş kodunu denetlemek ve ardından iki farklı değerden birini döndürmek için kullanılabildiğinden genellikle çok yararlı olur. Örneğin aşağıdaki kodda yer alan filtre, özel durumu yalnızca özel durum `STATUS_INTEGER_OVERFLOW` ise algılar:  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 Bu durumda koşullu işlecin amacı, temel olarak netlik sağlamaktır, çünkü aşağıdaki kod aynı sonuçları oluşturur:  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 Koşullu işleç daha -1, exceptıon_contınue_executıon değerlendirmek için filtre burada isteyebilirsiniz durumlarda faydalıdır.  
  
 Virgül işleci, tek bir ifade içerisinde birden fazla bağımsız işlemler gerçekleştirmenizi sağlar. Etkisi, kabaca birden fazla deyim yürütmeye ve ardından son ifadenin değerini döndürmeye benzerdir. Örneğin, aşağıdaki kod özel durum kodunu bir değişkende depolar ve ardından bunu test eder:  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)