---
title: __if_exists deyimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __if_exists_cpp
dev_langs: C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7950e2fcd933bd4748c06adf93f5ce1c271b162
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ifexists-statement"></a>__if_exists Deyimi
`__if_exists` Deyimi belirtilen tanımlayıcı var olup olmadığını sınar. Tanımlayıcı zaten varsa, belirtilen ifade bloğu yürütülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`identifier`|Varlığı test etmek istediğiniz tanımlayıcısı.|  
|`statements`|Varsa yürütmek için bir veya daha fazla deyimleri `identifier` bulunmaktadır.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  En güvenilir sonuçlar elde etmek için kullanmak `__if_exists` deyimi aşağıdaki kısıtlamalar altında.  
  
-   Uygulama `__if_exists` deyimi yalnızca basit türlere, şablon yok.  
  
-   Uygulama `__if_exists` deyimi içinde veya dışında bir sınıf tanımlayıcıları. Geçerli `__if_exists` yerel değişkenler ifadesine.  
  
-   Kullanım `__if_exists` deyimi yalnızca bir işlev gövdesi. Bir işlev gövdesi dışında `__if_exists` deyimi tam olarak tanımlı türler yalnızca test edebilirsiniz.  
  
-   Aşırı yüklenen işlevler için test ettiğinizde, belirli bir aşırı yük form için test edilemez.  
  
 Tamamlayan `__if_exists` ifadesi [__if_not_exists](../cpp/if-not-exists-statement.md) deyimi.  
  
## <a name="example"></a>Örnek  
 Hangi değil önerilir Bu örnek şablonları kullandığına dikkat edin.  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim deyimleri](../cpp/selection-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [__if_not_exists Deyimi](../cpp/if-not-exists-statement.md)