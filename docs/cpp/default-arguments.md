---
title: "Varsayılan bağımsız değişkenler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- function declarators
- functions [C++], default arguments
- declaring functions [C++], declarators
- default arguments
- arguments [C++], default
- defaults [C++], arguments
ms.assetid: d32cf516-05cb-4d4d-b169-92f5649fdfa2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88c341abab34595da58d435be28f50e86cb47403
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="default-arguments"></a>Varsayılan Bağımsız Değişkenler
Çoğu durumda işlevlerin, varsayılan bir değerin yeterli olmasını sağlayacak kadar sık kullanılan bağımsız değişkenleri vardır. Bunu çözmek için varsayılan bağımsız değişken özelliği, bir işlev için yalnızca belirli bir çağrıda anlamlı olan bağımsız değişkenleri belirtmeye izin verir. Bu kavramı göstermeye içinde sunulan örneği göz önünde bulundurun. [işlev aşırı yüklemesi](../cpp/function-overloading.md).  
  
```  
// Prototype three print functions.  
int print( char *s );                  // Print a string.  
int print( double dvalue );            // Print a double.  
int print( double dvalue, int prec );  // Print a double with a  
//  given precision.  
```  
  
 Birçok uygulamada, `prec` için makul bir varsayılan değer sağlanabilir ve iki işleve olan gereksinim ortadan kalkar:  
  
```  
// Prototype two print functions.  
int print( char *s );                    // Print a string.  
int print( double dvalue, int prec=2 );  // Print a double with a  
//  given precision.  
```  
  
 Uygulaması `print` işlevi değiştirildiğinde biraz yalnızca bir işlev türü için mevcut olgu yansıtacak şekilde **çift**:  
  
```  
// default_arguments.cpp  
// compile with: /EHsc /c  
  
// Print a double in specified precision.  
//  Positive numbers for precision indicate how many digits  
//  precision after the decimal point to show. Negative  
//  numbers for precision indicate where to round the number  
//  to the left of the decimal point.  
  
#include <iostream>  
#include <math.h>  
using namespace std;  
  
int print( double dvalue, int prec ) {  
   // Use table-lookup for rounding/truncation.  
   static const double rgPow10[] = {   
      10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1, 10E0,  
         10E1,  10E2,  10E3,  10E4, 10E5,  10E6  
   };  
   const int iPowZero = 6;  
   // If precision out of range, just print the number.  
   if( prec >= -6 && prec <= 7 )  
      // Scale, truncate, then rescale.  
      dvalue = floor( dvalue / rgPow10[iPowZero - prec] ) *  
      rgPow10[iPowZero - prec];  
   cout << dvalue << endl;  
   return cout.good();  
}  
```  
  
 Yeni `print` işlevini çağırmak için, aşağıdaki gibi bir kod kullanın:  
  
```  
print( d );    // Precision of 2 supplied by default argument.  
print( d, 0 ); // Override default argument to achieve other  
//  results.  
```  
  
 Varsayılan bağımsız değişkenler kullanırken aşağıdaki noktaları unutmayın:  
  
-   Varsayılan bağımsız değişkenler yalnızca izleyen bağımsız değişkenlerin çıkarıldığı işlev çağrılarında kullanılır — bunlar son bağımsız değişkenler olmalıdır. Bu nedenle aşağıdaki kod geçersizdir:  
  
    ```  
    int print( double dvalue = 0.0, int prec );  
    ```  
  
-   Tekrar tanımlama orijinaliyle aynı olsa bile, sonraki bildirimlerde varsayılan bir bağımsız değişken tekrar tanımlanamaz. Bu nedenle, aşağıdaki kod bir hata oluşturur:  
  
    ```  
    // Prototype for print function.  
    int print( double dvalue, int prec = 2 );  
  
    ...  
  
    // Definition for print function.  
    int print( double dvalue, int prec = 2 )  
    {  
    ...  
    }  
    ```  
  
     Bu koddaki sorun; tanımdaki işlev bildiriminin `prec`için varsayılan bağımsız değişkeni yeniden tanımlamasıdır.  
  
-   Sonraki bildirimlerde başka varsayılan bağımsız değişkenler eklenebilir.  
  
-   İşlev işaretleri için varsayılan bağımsız değişkenler sağlanabilir. Örneğin:  
  
    ```  
    int (*pShowIntVal)( int i = 0 );  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 