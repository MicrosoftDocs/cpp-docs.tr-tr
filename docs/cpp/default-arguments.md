---
title: Varsayılan Bağımsız Değişkenler
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], function
- function declarators
- functions [C++], default arguments
- declaring functions [C++], declarators
- default arguments
- arguments [C++], default
- defaults [C++], arguments
ms.assetid: d32cf516-05cb-4d4d-b169-92f5649fdfa2
ms.openlocfilehash: ef0c81501fe37bd27a23daf2dd1c58b3e6a4f6c0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221737"
---
# <a name="default-arguments"></a>Varsayılan Bağımsız Değişkenler

Çoğu durumda işlevlerin, varsayılan bir değerin yeterli olmasını sağlayacak kadar sık kullanılan bağımsız değişkenleri vardır. Bunu çözmek için varsayılan bağımsız değişken özelliği, bir işlev için yalnızca belirli bir çağrıda anlamlı olan bağımsız değişkenleri belirtmeye izin verir. Bu kavramı göstermek için [Işlev aşırı yüklemesi](../cpp/function-overloading.md)içinde sunulan örneği göz önünde bulundurun.

```cpp
// Prototype three print functions.
int print( char *s );                  // Print a string.
int print( double dvalue );            // Print a double.
int print( double dvalue, int prec );  // Print a double with a
//  given precision.
```

Birçok uygulamada, `prec` için makul bir varsayılan değer sağlanabilir ve iki işleve olan gereksinim ortadan kalkar:

```cpp
// Prototype two print functions.
int print( char *s );                    // Print a string.
int print( double dvalue, int prec=2 );  // Print a double with a
//  given precision.
```

İşlevin uygulanması, `print` türü için yalnızca bir işlevin var olduğunu göstermek için biraz değiştirilmiştir **`double`** :

```cpp
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

```cpp
print( d );    // Precision of 2 supplied by default argument.
print( d, 0 ); // Override default argument to achieve other
//  results.
```

Varsayılan bağımsız değişkenler kullanırken aşağıdaki noktaları unutmayın:

- Varsayılan bağımsız değişkenler yalnızca izleyen bağımsız değişkenlerin çıkarıldığı işlev çağrılarında kullanılır — bunlar son bağımsız değişkenler olmalıdır. Bu nedenle aşağıdaki kod geçersizdir:

    ```cpp
    int print( double dvalue = 0.0, int prec );
    ```

- Tekrar tanımlama orijinaliyle aynı olsa bile, sonraki bildirimlerde varsayılan bir bağımsız değişken tekrar tanımlanamaz. Bu nedenle, aşağıdaki kod bir hata oluşturur:

    ```cpp
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

- Sonraki bildirimlerde başka varsayılan bağımsız değişkenler eklenebilir.

- İşlev işaretleri için varsayılan bağımsız değişkenler sağlanabilir. Örnek:

    ```cpp
    int (*pShowIntVal)( int i = 0 );
    ```
