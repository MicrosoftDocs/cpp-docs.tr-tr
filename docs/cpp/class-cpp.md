---
title: sınıfı (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- class_cpp
dev_langs:
- CPP
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a3c3defdfb882db69f7789c97feba11d346e540
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405593"
---
# <a name="class-c"></a>class (C++)
**Sınıfı** anahtar sözcüğü bir sınıf türü bildirir veya sınıf türü bir nesneyi tanımlar.  
  
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
 *Şablon belirtimi*  
 İsteğe bağlı şablon belirtimleri. Daha fazla bilgi için [şablonları](templates-cpp.md).  
  
 *class*  
 **Sınıfı** anahtar sözcüğü.  
  
 *MS-decl-spec*  
 İsteğe bağlı depolama sınıfı belirtimi. Daha fazla bilgi için [__declspec](../cpp/declspec.md) anahtar sözcüğü.  
  
 *Etiket*  
 Sınıfı için verilen tür adı. Etiket sınıf kapsamı içinde ayrılmış bir sözcük haline gelir. Etiket isteğe bağlıdır. Atlanırsa, anonim bir sınıf tanımlanır. Daha fazla bilgi için [anonim sınıf türleri](../cpp/anonymous-class-types.md).  
  
 *temel-liste*  
 Sınıflar veya yapılar bu sınıf üyelerini derleyeceği isteğe bağlı bir liste. Bkz: [taban sınıfları](../cpp/base-classes.md) daha fazla bilgi için. Her temel sınıf veya yapı adı bir erişim belirticisi tarafından öncesinde ([genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md)) ve [sanal](../cpp/virtual-cpp.md) anahtar sözcüğü. Üye erişimi tabloya bakın [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) daha fazla bilgi için.  
  
 *üye listesi*  
 Sınıf üyeleri listesi. Başvurmak [sınıf üyelerine genel bakış](../cpp/class-member-overview.md) daha fazla bilgi için.  
  
 *Bildirimciler*  
 Sınıf türünün bir veya daha fazla örnek adlarını belirten bildirimci listesi. Bildirimciler, sınıfın tüm veri üyeleri ise Başlatıcı Listeleri içerebilir **genel**. Bu veri üyeleri, yapıları, daha sık olarak **genel** varsayılan olarak kıyasla sınıfları. Bkz: [genel bakış, Bildirimcileri](../cpp/overview-of-declarators.md) daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıflar hakkında daha fazla bilgi için genel olarak, aşağıdaki konulardan birine bakın:  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [birleşim](../cpp/unions.md)  
  
-   [__multiple_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__single_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__virtual_inheritance](../cpp/inheritance-keywords.md)  
  
 Yönetilen sınıflar ve yapı birimleri hakkında daha fazla bilgi için bkz: [sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)