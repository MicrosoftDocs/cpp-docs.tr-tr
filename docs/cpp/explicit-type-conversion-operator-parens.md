---
title: "Açık tür dönüştürme işleci: () | Microsoft Docs"
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
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 806a943ff9f5ebd0c6971340b66266aa7da9c0c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-type-conversion-operator-"></a>Açık Tür Dönüştürme İşleci: ()
C++, işlev çağrısı sözdizimine benzer bir sözdizimi kullanarak açık tür dönüştürme sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
simple-type-name ( expression-list )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 A *basit tür adı* arkasından bir *ifade listesinde* parantez yapılardan belirtilen ifadeler kullanarak belirtilen türde bir nesne içine alınmalıdır. Aşağıdaki örnekte, int türüne yapılan açık tür dönüştürme gösterilmektedir:  
  
```  
int i = int( d );  
```  
  
 Aşağıdaki örnekte gösterildiği bir `Point` sınıfı.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Explicit_Type_Conversion_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
public:  
    // Define default constructor.  
    Point() { _x = _y = 0; }  
    // Define another constructor.  
    Point( int X, int Y ) { _x = X; _y = Y; }  
  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
    void Show()   { cout << "x = " << _x << ", "  
                         << "y = " << _y << "\n"; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
int main()  
{  
    Point Point1, Point2;  
  
    // Assign Point1 the explicit conversion  
    //  of ( 10, 10 ).  
    Point1 = Point( 10, 10 );  
  
    // Use x() as an l-value by assigning an explicit  
    //  conversion of 20 to type unsigned.  
    Point1.x() = unsigned( 20 );  
    Point1.Show();  
  
    // Assign Point2 the default Point object.  
    Point2 = Point();  
    Point2.Show();  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 Yukarıdaki örnekte sabitler kullanılarak yapılan açık tür dönüştürme gösterilse de, aynı teknik bu dönüştürmeleri nesneler üzerinde gerçekleştirmek için de kullanılabilir. Aşağıdaki kod parçası bunu gösterir:  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 Açık tür dönüştürmeleri, "atama" sözdizimi kullanılarak da belirtilebilir. Atama sözdizimi kullanılarak yeniden yazılan yukarıdaki örnek şöyle olur:  
  
```  
d = (float)i;  
```  
  
 Hem atama hem de işlev stili dönüştürmelerin sonuçları, tek değerlerden dönüştürme gerçekleştirilirken aynı olur. Bununla birlikte, işlev stili sözdiziminde dönüştürme için birden fazla bağımsız değişken belirtebilirsiniz. Bu fark, kullanıcı tanımlı türler için önemlidir. Bir `Point` sınıfını ve dönüştürme işlemlerini göz önünde bulundurun:  
  
```  
struct Point  
{  
    Point( short x, short y ) { _x = x; _y = y; }  
    ...  
    short _x, _y;  
};  
...  
Point pt = Point( 3, 10 );  
```  
  
 İşlevi stili dönüştürme kullanır, önceki örnekte, iki değer dönüştürmek gösterilmektedir (biri *x* için bir tane *y*) için kullanıcı tanımlı tür `Point`.  
  
> [!CAUTION]
>  C++ derleyicisinin yerleşik tür denetimini geçersiz kıldıkları için açık tür dönüştürmelerini dikkatlice kullanın.  
  
 [Cast](../cpp/cast-operator-parens.md) gösterimi kullanılan, olmayan türlere dönüştürme için bir *basit tür adı* (işaretçi veya başvuru türleri, örneğin). İle ifade türleri dönüştürme bir *basit tür adı* her iki biçimde yazılabilir. Bkz: [tür tanımlayıcıları](http://msdn.microsoft.com/en-us/34b6c737-0ef1-4470-9b77-b26e46c0bbd4) nelerin oluşturduğunu hakkında daha fazla bilgi için bir *basit tür adı*.  
  
 Atamalar içinde tür tanımı olamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonek ifadeleri](../cpp/postfix-expressions.md)   
 [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)