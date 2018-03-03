---
title: "typeid işleci | Microsoft Docs"
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
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b27f3bcb7358b3ea05907df1a4372c107538dfb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="typeid-operator"></a>typeid İşleci
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `typeid` işleci nesnenin türünün çalışma zamanında belirlenmesine izin verir.  
  
 Sonucu `typeid` olan bir **const type_info &**. Bir başvuru değeri olan bir **type_info** ya da temsil eden nesne *türü kimliği* veya türü *ifade*hangi biçiminin bağlı olarak `typeid` kullanılır . Bkz: [type_info sınıfı](../cpp/type-info-class.md) daha fazla bilgi için.  
  
 `typeid` İşleci (soyut Bildirimciler veya örnekleri) yönetilen türleriyle çalışmaz, bkz: [TypeID](../windows/typeid-cpp-component-extensions.md) alma hakkında bilgi için <xref:System.Type> belirli bir türde.  
  
 `typeid` işleci, doğru nesne türünün sağlanan statik bilgilerle belirlenemediği çok biçimli bir sınıf türünün l- değerine uygulandığında bir çalışma zamanı denetimi yapar. Bu gibi durumlar şunlardır:  
  
-   Bir sınıf başvurusu  
  
-   * ile başvurusu kaldırılmış bir işaretçi  
  
-   Bir alt işaretçi (diğer bir deyişle [ ]). (Bir çok biçimli türün işaretçisi ile bir alt simge kullanmanın genellikle güvenli olmadığını unutmayın.)  
  
 Varsa *ifade* nesne gerçekte bu temel sınıfından türetilmiş bir türün yine de bir taban sınıf türü için işaret bir **type_info** türetilmiş sınıf sonucu için başvuru. *İfade* çok biçimli bir türü (sanal işlevler sınıfıyla) işaret etmelidir. Aksi takdirde, sonuç değer **type_info** başvurulan statik sınıf için *ifade*. Ayrıca, işaretçinin işaret ettiği nesnenin kullanılabilmesi için işaretçinin başvurusu kaldırılmalıdır. İşaretçi başvurusunun kaldırılmasının olmadan sonucu olacaktır **type_info** hangi BT işaretçisi işaret. Örneğin:  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 Varsa *ifade* bir işaretçi başvurusunun kaldırılmasının ve işaretçinin değeri sıfır ise **TypeID** oluşturur bir [bad_typeid özel durumu](../cpp/bad-typeid-exception.md). İşaretçinin geçerli bir nesneye işaret etmiyorsa bir `__non_rtti_object` özel durum, bir arıza tetiklenen RTTI analiz denemesi belirten (ister erişim ihlali), nesne şekilde geçersiz olduğundan (geçersiz işaretçi veya kod değildi derlenmiş ile[/GR](../build/reference/gr-enable-run-time-type-information.md)).  
  
 Varsa *ifade* ne bir işaretçi ne de bir temel sınıf nesnenin başvuru sonucu olan bir **type_info** statik türünü temsil eden başvuru *ifade*. *Statik türü* derleme zamanında bilinen bir ifadenin bir ifade türüne başvuruyor. Yürütme semantikleri, bir ifadenin statik türü değerlendirilirken göz ardı edilir. Ayrıca, bir ifadenin statik türü belirlenirken, mümkün olduğunca başvurular da dikkate alınmaz:  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **TypeId** şablonlarında şablon parametresi türünü belirlemek için de kullanılabilir:  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)