---
title: "static_cast işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: static_cast_cpp
dev_langs: C++
helpviewer_keywords: static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d04c49076f5189e913c8755a5bce4d7e5c7daf11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="staticcast-operator"></a>static_cast İşleci
Dönüştürür bir *ifade* türüne *türü kimliği* ifadesinde bulunan türüne göre.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Standart C++ kapsamında, dönüştürmenin güvenliğini sağlamaya yardımcı olmak için bir çalışma zamanı tür denetimi yapılmaz. C++/CX kapsamında, derleme zamanı ve çalışma zamanı denetimi gerçekleştirilir. Daha fazla bilgi için bkz: [atama](casting.md).  
  
 `static_cast` İşleci, türetilmiş bir sınıf için bir işaretçi için temel sınıf için bir işaretçi dönüştürme gibi işlemleri için kullanılabilir. Bu tür dönüştürmeler her zaman güvenli değildir.  
  
 Genel olarak kullandığınız `static_cast` ints veya ints float ve numaralandırmaları gibi sayısal veri türleri dönüştürmek istediğiniz zaman belirli veri türlerini dönüştürme ilgilidir. `static_cast`dönüşümler olarak güvenli olmayan `dynamic_cast` dönüşümleri, çünkü `static_cast` çalışma zamanı tür kontrol etmez, ancak `dynamic_cast` yapar. A `dynamic_cast` belirsiz bir işaretçi başarısız olur, ancak bir `static_cast` hiçbir şey tehlikeli olabilir; yanlış olarak döndürür. Ancak `dynamic_cast` dönüşümleri daha güvenli, `dynamic_cast` işaretçileri veya başvuruları ve çalışma zamanı tür denetimi üzerinde çalışır bir ek yük, yalnızca. Daha fazla bilgi için bkz: [dynamic_cast işleci](../cpp/dynamic-cast-operator.md).  
  
 Satırın aşağıdaki örnekteki `D* pd2 = static_cast<D*>(pb);` güvenli değildir çünkü `D` alanları ve bulunmayan yöntemleri olabilir `B`. Ancak, satır `B* pb2 = static_cast<B*>(pd);` güvenli dönüştürme çünkü `D` her zaman tüm içeren `B`.  
  
```  
// static_cast_Operator.cpp  
// compile with: /LD  
class B {};  
  
class D : public B {};  
  
void f(B* pb, D* pd) {  
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields  
                                   // and methods that are not in B.  
  
   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always  
                                   // contains all of B.  
}  
```  
  
 Tersine için [dynamic_cast](../cpp/dynamic-cast-operator.md), çalışma zamanı Denetimsiz üzerinde yapılan `static_cast` dönüştürülmesi `pb`. Tarafından için nesne işaret `pb` türünde bir nesne olmayabilir `D`, bu durumda kullanımını `*pd2` felaket niteliğinde olabilir. Örneğin, bir işlevi çağıran bir üyesidir `D` sınıfı değil, `B` sınıfı, bir erişim ihlali neden olabilir.  
  
 `dynamic_cast` Ve `static_cast` işleçleri bir işaretçi bir sınıf hiyerarşisi boyunca taşıyın. Ancak, `static_cast` özel olarak cast bildiriminde sağlanan bilgileri kullanır ve bu nedenle güvenli olabilir. Örneğin:  
  
```  
// static_cast_Operator_2.cpp  
// compile with: /LD /GR  
class B {  
public:  
   virtual void Test(){}  
};  
class D : public B {};  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  
   D* pd2 = static_cast<D*>(pb);  
}  
```  
  
 Varsa `pb` gerçekten, türünde bir nesneye işaret `D`, ardından `pd1` ve `pd2` aynı değerini alır. Bunlar da aynı değere alırsa `pb == 0`.  
  
 Varsa `pb` türünde bir nesneye işaret `B` ve tam `D` sınıfı, ardından `dynamic_cast` yeterli sıfır döndürülecek öğrenmiş olacaksınız. Ancak, `static_cast` Programcı onaylama üzerinde kullanır, `pb` türünde bir nesneye işaret `D` ve yalnızca bir işaretçi için beklenen döndüren `D` nesnesi.  
  
 Sonuç olarak, `static_cast` örtük dönüşümler tersini yapabilmeniz için bu durumda sonuçları tanımlanmamış. Sonuçlarını doğrulamak için programcı bırakılır bir `static_cast` dönüştürme güvenli.  
  
 Bu davranış, sınıf türleri dışındaki türler için de geçerlidir. Örneğin, `static_cast` int'e dönüştürmek için kullanılan bir `char`. Ancak, elde edilen `char` tüm tutmak için yeterli BITS olmayabilir `int` değeri. Sonuçları doğrulamak için programcı yeniden bırakılır bir `static_cast` dönüştürme güvenli.  
  
 `static_cast` İşleci ayrıca standart dönüştürmeler ve kullanıcı tanımlı dönüşümler dahil olmak üzere tüm örtük dönüştürme gerçekleştirmek için kullanılabilir. Örneğin:  
  
```  
// static_cast_Operator_3.cpp  
// compile with: /LD /GR  
typedef unsigned char BYTE;  
  
void f() {  
   char ch;  
   int i = 65;  
   float f = 2.5;  
   double dbl;  
  
   ch = static_cast<char>(i);   // int to char  
   dbl = static_cast<double>(f);   // float to double  
   i = static_cast<BYTE>(ch);  
}  
```  
  
 `static_cast` İşleci bir numaralandırma türü için bir tam sayı değeri açıkça dönüştürebilirsiniz. Tamsayı türünün değeri, numaralandırma değerleri aralığı içinde kalmıyorsa, sonuç olarak elde edilen numaralandırma değeri tanımsızdır.  
  
 `static_cast` İşleci hedef türü null işaretçinin değeri boş işaretçi değeri dönüştürür.  
  
 Herhangi bir ifade türü void tarafından açıkça dönüştürülebilir `static_cast` işleci. Hedef void türüne isteğe bağlı olarak dahil edebilirsiniz `const`, `volatile`, veya `__unaligned` özniteliği.  
  
 `static_cast` İşleci olamaz atama dışarıda `const`, `volatile`, veya `__unaligned` öznitelikleri. Bkz: [const_cast işleci](../cpp/const-cast-operator.md) bu öznitelikler kaldırma hakkında bilgi için.  
  
 İşaretli atamaları relocating bir atık toplayıcı kullanımını üstte gerçekleştirmenin tehlike nedeniyle `static_cast` düzgün çalışır yalnızca performans açısından kritik kod içinde olması gerekir. Kullanmanız gerekiyorsa `static_cast` yayın modunda ile yerine [safe_cast](../windows/safe-cast-cpp-component-extensions.md) başarılı olmak için hata ayıklama derlemelerinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama İşleçleri](../cpp/casting-operators.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)