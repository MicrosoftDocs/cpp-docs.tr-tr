---
title: "İşlev çağrısı (C++) | Microsoft Docs"
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
- function calls, C++ functions
- functions [C++], calling
- operator overloading [C++], function calls
- function overloading [C++], function-call operator
- function calls, operator
- operators [C++], overloading
- operator overloading [C++], examples
- function call operator ()
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6d130f087f635306083e58faf7c77b252fc9360
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="function-call-c"></a>İşlev Çağrısı (C++)
Parantez kullanılarak çağrılan işlev çağrısı işleci, ikili bir işleçtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
primary-expression ( expression-list )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bağlamda `primary-expression` ilk işleneni ve `expression-list`, büyük olasılıkla boş bağımsız değişken listesini ikinci işlenen içerir. İşlev çağrısı işleci, birkaç parametre gerektiren işlemler için kullanılır. Bu çalışır çünkü `expression-list` yerine tek bir işlenen listesidir. İşlev çağrısı işleci, statik olmayan bir üye işlevi olmalıdır.  
  
 İşlev çağrısı işleci, aşırı yüklendiğinde işlevlerin çağrılma biçimini değiştirmez; bunun yerine, işlecin belirli bir sınıf türünden nesnelere uygulandığında nasıl yorumlanacağını değiştirir. Örneğin, aşağıdaki kod genellikle anlamsız olacaktır:  
  
```  
Point pt;  
pt( 3, 2 );  
```  
  
 Uygun aşırı yüklenmiş işlev çağırma işleci verildiğinde, ancak, bu söz dizimini dengelemek için kullanılabilir `x` 3 birimleri koordine ve `y` 2 birim koordinatı. Aşağıdaki kod, bu tür bir tanımı göstermektedir:  
  
```  
// function_call.cpp  
class Point  
{  
public:  
    Point() { _x = _y = 0; }  
    Point &operator()( int dx, int dy )  
        { _x += dx; _y += dy; return *this; }  
private:  
    int _x, _y;  
};  
  
int main()  
{  
   Point pt;  
   pt( 3, 2 );  
}  
```  
  
 İşlev çağrısı işlecinin bir işlevin adına değil, bir nesnenin adına uygulandığını unutmayın.  
  
 Ayrıca, bir işlev (işlevi yerine) için bir işaretçi kullanarak işlev çağırma işleci aşırı yüklenebilir.  
  
```cpp  
typedef void(*ptf)();  
void func()  
{  
}  
struct S  
{  
   operator ptf()  
   {  
      return func;  
   }  
};  
  
int main()  
{  
   S s;  
   s();//operates as s.operator ptf()()  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)