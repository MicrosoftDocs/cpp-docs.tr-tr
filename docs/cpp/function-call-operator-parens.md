---
title: 'İşlev çağırma işleci: () | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b0c4cde0c50064c5a88469e8f9061a0321902e4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408589"
---
# <a name="function-call-operator-"></a>İşlev Çağırma İşleci: ()
İşlev çağrısı işleci bir sonek ifadesi **()**, bir işlev çağrısı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Virgülle ayrılmış ifadeler sıfır veya daha fazla işlev çağrısı işlecinin bağımsız değişkenler — gerçek bağımsız değişkenler işleve.  
  
 *Sonek ifadesi* bir işlev adresini (örneğin, bir işlev Belirleyicisi veya işlev işaretçisinin değeri) değerlendirmelidir ve *bağımsız değişken ifade listesi* (ayrılmış ifadeler listesi virgülle) değerleri (bağımsız değişkenleri) işleve geçirilir. *Bağımsız değişken ifade listesi* bağımsız değişkeni boş olabilir.  
  
 *Sonek ifadesi* bu türlerden biri olmalıdır:  
  
-   Türü döndüren bir işlev `T`. Örnek bildirimi şu şekildedir  
  
    ```cpp 
    T func( int i )  
    ```  
  
-   Türü döndüren bir işlev işaretçisine `T`. Örnek bildirimi şu şekildedir  
  
    ```cpp 
    T (*func)( int i )  
    ```  
  
-   Başvuru türü döndüren bir işlevin `T`. Örnek bildirimi şu şekildedir  
  
    ```cpp 
    T (&func)(int i)  
    ```  
  
-   İşaretçi-üye işlev döndürme türü başvuru `T`. Örnek işlev çağrıları  
  
    ```cpp 
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek standart kitaplık işlevini çağırır `strcat_s` üç bağımsız değişken ile:  
  
```cpp 
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// C++ Standard Library name space  
using namespace std;  
  
int main()  
{  
    enum  
    {  
        sizeOfBuffer = 20  
    };  
  
    char s1[ sizeOfBuffer ] = "Welcome to ";  
    char s2[ ] = "C++";  
  
    strcat_s( s1, sizeOfBuffer, s2 );  
  
    cout << s1 << endl;  
}  
```  
  
```Output  
Welcome to C++  
```  
  
## <a name="function-call-results"></a>İşlev çağrısı sonuçları  
 Bir başvuru türü işlev bildirildiği sürece bir işlev çağrısı için bir r değerlendirir. Başvuru dönüş türü içeren işlevler l-değerler ve atama deyiminin sol tarafında aşağıdaki gibi kullanılabilir:  
  
```cpp 
// expre_Function_Call_Results.cpp  
// compile with: /EHsc  
#include <iostream>  
class Point  
{  
public:  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
using namespace std;  
int main()  
{  
    Point ThePoint;  
  
    ThePoint.x() = 7;           // Use x() as an l-value.  
    unsigned y = ThePoint.y();  // Use y() as an r-value.  
  
    // Use x() and y() as r-values.  
    cout << "x = " << ThePoint.x() << "\n"  
         << "y = " << ThePoint.y() << "\n";  
}  
```  
  
 Yukarıdaki kod adında bir sınıf tanımlar `Point`, özel veri içeren temsil eden nesneleri *x* ve *y* koordinatları. Bu veri nesneleri değiştirilmesi gerekir ve bunların değerlerini alınır. Bu program yalnızca bu tür bir sınıf için birkaç tasarımlar biridir; Kullanım `GetX` ve `SetX` veya `GetY` ve `SetY` işlevleri, başka bir olası tasarım.  
  
 Bu dönüş sınıf türleri İşlevler, sınıf türleri için işaretçiler veya başvurular sınıf türleri için üye seçim işleçleri sol işleneni olarak kullanılabilir. Bu nedenle, aşağıdaki kod geçerlidir:  
  
```cpp 
// expre_Function_Results2.cpp  
class A {  
public:  
   A() {}  
   A(int i) {}  
   int SetA( int i ) {  
      return (I = i);  
   }  
  
   int GetA() {  
      return I;  
   }  
  
private:  
   int I;  
};  
  
A func1() {  
   A a = 0;  
   return a;  
}  
  
A* func2() {  
   A *a = new A();  
   return a;  
}  
  
A& func3() {  
   A *a = new A();  
   A &b = *a;  
   return b;  
}  
  
int main() {  
   int iResult = func1().GetA();  
   func2()->SetA( 3 );  
   func3().SetA( 7 );  
}  
```  
  
 Özyinelemeli işlevler çağrılabilir. İşlev bildirimleri hakkında daha fazla bilgi için bkz: [işlevleri](functions-cpp.md). İlgili malzeme konusu [Program ve bağlantı](../cpp/program-and-linkage-cpp.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Sonek ifadeleri](../cpp/postfix-expressions.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [İşlev Çağrısı](../c-language/function-call-c.md)   