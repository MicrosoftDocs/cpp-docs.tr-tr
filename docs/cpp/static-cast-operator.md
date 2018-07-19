---
title: static_cast işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- static_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad9af76787780ebe2a25b3fab46ce1951085b8e8
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948208"
---
# <a name="staticcast-operator"></a>static_cast İşleci
Dönüştürür bir *ifade* türüne *tür kimliği* yalnızca ifadede bulunan türlere göre.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Standart C++ kapsamında, dönüştürmenin güvenliğini sağlamaya yardımcı olmak için bir çalışma zamanı tür denetimi yapılmaz. C++/CX kapsamında, derleme zamanı ve çalışma zamanı denetimi gerçekleştirilir. Daha fazla bilgi için [atama](casting.md).  
  
 **Static_cast** işleci, bir temel sınıftan türetilmiş bir sınıf işaretçisine dönüştürme gibi işlemler için kullanılabilir. Bu tür dönüştürmeler her zaman güvenli değildir.  
  
 Genel olarak kullandığınız **static_cast** tamsayılara ya da tamsayıları kayanlara float'ların ve numaralandırmalar gibi sayısal veri türlerini dönüştürmek istediğinizde belirli veri türlerinin ve dönüştürmeye dahil. **static_cast** dönüştürmeleri kadar güvenli olmayan **dynamic_cast** dönüştürmeler, çünkü **static_cast** hiçbir çalışma zamanı tür denetimi yapmadığından **dynamic_cast** yapar. A **dynamic_cast** belirsiz bir işaretçiye başarısız olur, ancak bir **static_cast** hiçbir şey yanlış; bu tehlikeli olabilir değilmiş gibi döndürülürken. Ancak **dynamic_cast** dönüştürmeleri daha güvenli, **dynamic_cast** yalnızca çalışır işaretçiler veya başvurular ve çalışma zamanı tür denetimi bir ek yüktür. Daha fazla bilgi için [dynamic_cast işleci](../cpp/dynamic-cast-operator.md).  
  
 Satırın aşağıdaki örnekteki `D* pd2 = static_cast<D*>(pb);` güvenli değildir çünkü `D` alanları ve olmayan yöntemleri olabilir `B`. Ancak, satır `B* pb2 = static_cast<B*>(pd);` güvenli bir dönüştürmedir `D` her zaman tüm içeren `B`.  
  
```cpp 
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
  
 Tersine [dynamic_cast](../cpp/dynamic-cast-operator.md), hiçbir çalışma zamanı denetimi yapılmaz **static_cast** dönüştürülmesi `pb`. Nesne tarafından işaret edilen `pb` türünde bir nesne olmayabilir `D`, bu durumda kullanımını `*pd2` çok kötü sonuçlar doğurabilir. Örneğin, bir üyesi olan bir işlevi çağırmak `D` sınıfının değil, `B` sınıfı, bir erişim ihlali ile sonuçlanabilir.  
  
 **Dynamic_cast** ve **static_cast** işleçleri bir işaretçiyi bir sınıf hiyerarşisi boyunca taşır. Ancak, **static_cast** özellikle cast deyiminde sağlanan bilgilere dayanır ve bu nedenle güvenli olmayabilir. Örneğin:  
  
```cpp 
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
  
 Varsa `pb` gerçekten, türü bir nesneye işaret `D`, ardından `pd1` ve `pd2` aynı değeri alacaktır. Bunlar ayrıca aynı değeri alırsa `pb == 0`.  
  
 Varsa `pb` türündeki bir nesneye işaret `B` tam `D` sınıfını **dynamic_cast** öğesi sıfır döndürmek yeterince bilgi sahibi olacaktır. Ancak, **static_cast** Programcı onayına güvenir, `pb` türündeki bir nesneye işaret `D` ve konusu yalnızca işaretçi döndüren `D` nesne.  
  
 Sonuç olarak, **static_cast** örtük dönüştürmelerin tersini yapabilir, bu durumda sonuçlar tanımsızdır. Sonuçları olduğunu doğrulamak programcıya bırakılır bir **static_cast** güvenli.  
  
 Bu davranış, sınıf türleri dışındaki türler için de geçerlidir. Örneğin, **static_cast** int'e dönüştürmek için kullanılan bir **char**. Ancak, elde edilen **char** tamamını tutmak için yeterli bite sahip olmayabilir **int** değeri. Bu sonuçları olduğunu doğrulamak programcıya yeniden bırakılır bir **static_cast** güvenli.  
  
 **Static_cast** işleci ayrıca standart dönüştürmeler veya kullanıcı tanımlı dönüştürmeler de dahil olmak üzere herhangi bir örtük dönüştürmeyi gerçekleştirmek için kullanılabilir. Örneğin:  
  
```cpp 
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
  
 **Static_cast** işleci bir tamsayı değeri açıkça bir sayma türüne dönüştürebilir. Tamsayı türünün değeri, numaralandırma değerleri aralığı içinde kalmıyorsa, sonuç olarak elde edilen numaralandırma değeri tanımsızdır.  
  
 **Static_cast** işlecini bir null işaretçi değeri hedef türünün boş işaretçi değerine dönüştürür.  
  
 Herhangi bir ifade tarafından void türüne açıkça dönüştürülebilir **static_cast** işleci. Hedef void türü isteğe bağlı olarak içerebilir **const**, **geçici**, veya **__unaligned** özniteliği.  
  
 **Static_cast** işleci beklenmedik şekilde atayamaz **const**, **geçici**, veya **__unaligned** öznitelikleri. Bkz: [const_cast işleci](../cpp/const-cast-operator.md) bu öznitelikleri kaldırma hakkında bilgi için.  
  
 Yeniden konumlandırma atık Toplayıcıya, kullanımını üstte denetlenmeyen yayınlar gerçekleştirme tehlikesi nedeniyle **static_cast** düzgün çalışır emin olduğunuzda yalnızca performans açısından kritik kodda olmalıdır. Kullanmanız gerekirse **static_cast** yayın modunda ile yerine [safe_cast](../windows/safe-cast-cpp-component-extensions.md) başarı sağlamak için hata ayıklama yapılarınızda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama İşleçleri](../cpp/casting-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)