---
title: "sınıfı (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: class_cpp
dev_langs: CPP
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed344d5c15e709b09b760dee74a986dde6383d22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="class-c"></a>class (C++)
`class` Anahtar sözcüğü bir sınıf türü bildirir ya da bir sınıf türünde bir nesne tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `template-spec`  
 İsteğe bağlı şablon belirtimleri. Daha fazla bilgi için bkz [şablonları](templates-cpp.md).  
  
 `class`  
 `class` Anahtar sözcüğü.  
  
 `ms-decl-spec`  
 İsteğe bağlı depolama sınıfı belirtimi. Daha fazla bilgi için bkz [__declspec](../cpp/declspec.md) anahtar sözcüğü.  
  
 `tag`  
 Sınıfı için verilen tür adı. Sınıf kapsamı içinde ayrılmış bir sözcük etiketi olur. Etiket isteğe bağlıdır. Anonim sınıf atlanırsa, tanımlanır. Daha fazla bilgi için bkz: [anonim sınıf türleri](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Sınıflar ya da bu sınıf, üyelerinden elde yapıları isteğe bağlı listesi. Bkz: [taban sınıfları](../cpp/base-classes.md) daha fazla bilgi için. Her temel sınıf veya yapı adı bir erişim belirteci tarafından gelmesi ([ortak](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md)) ve [sanal](../cpp/virtual-cpp.md) anahtar sözcük. Üye erişimi tablosunda görmek [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) daha fazla bilgi için.  
  
 `member-list`  
 Sınıf üyeleri listesi. Başvurmak [sınıf üyelerine genel bakış](../cpp/class-member-overview.md) daha fazla bilgi için.  
  
 `declarators`  
 Sınıf türü bir veya daha fazla örneğinin adını belirterek bildirimcisi listesi. Bildirimler, başlatıcı listeleri içerebilir, sınıfın tüm veri üyesi `public`. Veri üyeleri yapılarda daha yaygın budur `public` biçimde varsayılan sınıfları. Bkz: [genel bakış, Bildirimciler](../cpp/overview-of-declarators.md) daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfları hakkında daha fazla bilgi için genel olarak, aşağıdaki konulardan birine bakın:  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [birleşim](../cpp/unions.md)  
  
-   [__multiple_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__single_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__virtual_inheritance](../cpp/inheritance-keywords.md)  
  
 Yönetilen sınıflar ve yapılar hakkında daha fazla bilgi için bkz: [sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)  
  
## <a name="example"></a>Örnek  
  
```  
// class.cpp  
// compile with: /EHsc  
// Example of the class keyword  
// Exhibits polymorphism/virtual functions.  
  
#include <iostream>  
#include <string>  
#define TRUE = 1  
using namespace std;  
  
class dog  
{  
public:  
   dog()  
   {  
      _legs = 4;  
      _bark = true;  
   }  
  
   void setDogSize(string dogSize)  
   {  
      _dogSize = dogSize;  
   }  
   virtual void setEars(string type)      // virtual function  
   {  
      _earType = type;  
   }  
  
private:  
   string _dogSize, _earType;  
   int _legs;  
   bool _bark;  
  
};  
  
class breed : public dog  
{  
public:  
   breed( string color, string size)  
   {  
      _color = color;  
      setDogSize(size);  
   }  
  
   string getColor()  
   {  
      return _color;  
   }  
  
   // virtual function redefined  
   void setEars(string length, string type)  
   {  
      _earLength = length;  
      _earType = type;  
   }  
  
protected:  
   string _color, _earLength, _earType;  
};  
  
int main()  
{  
   dog mongrel;  
   breed labrador("yellow", "large");  
   mongrel.setEars("pointy");  
   labrador.setEars("long", "floppy");  
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)