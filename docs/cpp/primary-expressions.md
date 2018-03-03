---
title: Birincil ifadeler | Microsoft Docs
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
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a6e811e1fe074ce488b09fca29926989bc7f355
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="primary-expressions"></a>Birincil İfadeler
Birincil ifadeler daha karmaşık ifadelerin yapı taşlarıdır. Değişmez değerler, adları ve kapsam çözümü işleci tarafından nitelenmiş adlar oldukları (`::`).  Birincil bir ifade aşağıdaki biçimlerden birini içerebilir:  
  
```  
  
      literal  
      this  
:: namename( expression )  
```  
  
 A *değişmez değer* sabit bir birincil ifadesidir. Türü kendi belirtiminin biçimine bağlıdır. Bkz: [değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md) değişmez değerleri belirtme hakkında tam bilgi için.  
  
 **Bu** bir sınıf nesnesi için bir işaretçi bir anahtardır. Statik olmayan üye işlevlerinde kullanılabilir ve işlevin çağrıldığı sınıfın örneğini gösterir. **Bu** anahtar sözcüğü bir sınıf üyesi işlevinin gövdesini dışında kullanılamaz.  
  
 Türü **bu** işaretçi `type`  **\*const** (burada `type` sınıfı adı) özellikle değiştirme işlevleri içinde **bu** işaretçi. Aşağıdaki örnek üye işlev bildirimleri ve türlerini gösterir **bu**:  
  
```  
// expre_Primary_Expressions.cpp  
// compile with: /LD  
class Example  
{  
public:  
    void Func();          //  * const this  
    void Func() const;    //  const * const this  
    void Func() volatile; //  volatile * const this  
};  
```  
  
 Bkz: [Bu işaretçinin](this-pointer.md) türünü değiştirme hakkında daha fazla bilgi için **bu** işaretçi.  
  
 Kapsam çözümü işleci (`::`) ve ardından birincil bir ifadenin bir ad oluşturduğunu.  Bu gibi adlar üye adları değil, genel kapsamdaki adlar olmalıdır.  Bu ifadenin türü adın bildirimi tarafından belirlenir. Bildirim adı lvalue ise, bu bir lvalue olur (diğer bir deyişle, bir atama işleci ifadesinin sol tarafında görünebilir). Söz konusu ad geçerli kapsamda gizlenmiş olsa da, kapsam çözümleme işleci başvurulacak bir genel bir ad sağlar. Bkz: [kapsam](../cpp/scope-visual-cpp.md) kapsam çözümü işleci kullanma örneği.  
  
 Parantez içine alınmış bir ifade, türü ve değeri parantez içinde olmayan ifadelerle aynı olan birincil bir ifadedir. Parantez içinde olmayan bir ifade bir lvalue ise, bu bir l-value olur.  
  
 Yukarıda verilen birincil ifade sözdizimini bağlamında *adı* için açıklanan sözdiziminde herhangi bir şey anlamına gelir [adları](http://msdn.microsoft.com/en-us/1c49cc24-08d5-4884-b170-ba8ed42d80db), ancak ne zaman adları tür adından önce kapsam çözümü işleci kullanılarak yalnızca oluşabilir bir sınıf içinde izin verilmez.  Buna kullanıcı tanımlı dönüştürme işlevi ve yok edici adları da dahildir.  
  
 Birincil ifadenin örnekleri şunlardır:  
  
```  
100 // literal  
'c' // literal  
this // in a member function, a pointer to the class instance  
::func // a global function  
::operator + // a global operator function  
::A::B // a global qualified name  
( i + 1 ) // a parenthesized expression  
```  
  
 Aşağıdaki örneklerde tüm kabul edilen *adları*ve bu nedenle birincil ifadeler, çeşitli formlar:  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade Türleri](../cpp/types-of-expressions.md)