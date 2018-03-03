---
title: "İşlev çağırma işleci: () | Microsoft Docs"
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
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa2a61dff4f20c5da7157a8a60700d9a8a10c06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="function-call-operator-"></a>İşlev Çağırma İşleci: ()
İşlev çağırma işleci tarafından izlenen bir sonek ifadesi **()**, bir işlev çağrısı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Virgülle ayrılmış sıfır veya daha fazla ifade işlev çağırma işleci için bağımsız değişkenler — işlevine gerçek bağımsız değişkenler.  
  
 *Sonek ifade* bir işlev adresi (örneğin, bir işlev tanımlayıcısı veya bir işlev işaretçisi değerini) değerlendirmeniz gerekir ve *bağımsız değişken ifadesi listesi* ifadeleri (ayrılmış bir listesi virgül tarafından) değerleri (bağımsız değişkenler) işlevine geçirilir. *Bağımsız değişken ifadesi listesi* bağımsız değişkeni boş olamaz.  
  
 *Sonek ifade* bu türlerden biri olmalıdır:  
  
-   Türü döndüren işlev `T`. Bir örnek bildirimi  
  
    ```  
    T func( int i )  
    ```  
  
-   Türü döndüren bir işlev işaretçisi `T`. Bir örnek bildirimi  
  
    ```  
    T (*func)( int i )  
    ```  
  
-   Başvuru türü döndüren bir işlev `T`. Bir örnek bildirimi  
  
    ```  
    T (&func)(int i)  
    ```  
  
-   İşaretçi-üye fonksiyonu başvuru döndürmeyi türü `T`. Örnek işlev çağrıları  
  
    ```  
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek standart kitaplığı işlevi çağırır `strcat_s` üç bağımsız değişken:  
  
```  
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
 İşlevi bir başvuru türü olarak bildirilmiş sürece bir işlev çağrısı için bir r değerlendirir. Başvuru dönüş türü işlevleriyle l-değerlerini değerlendirmek ve Atama ifadesinin sol tarafta gibi kullanılabilir:  
  
```  
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
  
 Önceki kod adlı bir sınıf tanımlar `Point`, özel veri içeren temsil eden nesneler *x* ve *y* koordinatları. Bu veri nesneleri değiştirilmesi gerekir ve bunların değerleri alınır. Bu program yalnızca bu tür bir sınıf için birkaç tasarımlar biridir; kullanımı `GetX` ve `SetX` veya `GetY` ve `SetY` işlevleri başka bir olası tasarım;.  
  
 Bu dönüş sınıf türleri İşlevler, sınıf türleri işaretçiler veya sınıf türleri başvuruları üye seçim işleçleri için sol işleneni olarak kullanılabilir. Bu nedenle, aşağıdaki kodu uygundur:  
  
```  
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
  
 Yinelemeli işlevler çağrılabilir. İşlev bildirimleri hakkında daha fazla bilgi için bkz: [işlevler](functions-cpp.md). İlgili malzeme konusu [Program ve bağlantı](../cpp/program-and-linkage-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonek ifadeleri](../cpp/postfix-expressions.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [İşlev çağrısı](../c-language/function-call-c.md)   
