---
title: class (C++)
ms.date: 11/04/2016
f1_keywords:
- class_cpp
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
ms.openlocfilehash: c4ef9690a41737147354ee0976f6912c4711ff67
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774821"
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

*Şablon belirtimi*<br/>
İsteğe bağlı şablon belirtimleri. Daha fazla bilgi için [şablonları](templates-cpp.md).

*class*<br/>
**Sınıfı** anahtar sözcüğü.

*MS-decl-spec*<br/>
İsteğe bağlı depolama sınıfı belirtimi. Daha fazla bilgi için [__declspec](../cpp/declspec.md) anahtar sözcüğü.

*Etiket*<br/>
Sınıfı için verilen tür adı. Etiket sınıf kapsamı içinde ayrılmış bir sözcük haline gelir. Etiket isteğe bağlıdır. Atlanırsa, anonim bir sınıf tanımlanır. Daha fazla bilgi için [anonim sınıf türleri](../cpp/anonymous-class-types.md).

*temel-liste*<br/>
Sınıflar veya yapılar bu sınıf üyelerini derleyeceği isteğe bağlı bir liste. Bkz: [taban sınıfları](../cpp/base-classes.md) daha fazla bilgi için. Her temel sınıf veya yapı adı bir erişim belirticisi tarafından öncesinde ([genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md)) ve [sanal](../cpp/virtual-cpp.md) anahtar sözcüğü. Üye erişimi tabloya bakın [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) daha fazla bilgi için.

*üye listesi*<br/>
Sınıf üyeleri listesi. Başvurmak [sınıf üyelerine genel bakış](../cpp/class-member-overview.md) daha fazla bilgi için.

*Bildirimciler*<br/>
Sınıf türünün bir veya daha fazla örnek adlarını belirten bildirimci listesi. Bildirimciler, sınıfın tüm veri üyeleri ise Başlatıcı Listeleri içerebilir **genel**. Bu veri üyeleri, yapıları, daha sık olarak **genel** varsayılan olarak kıyasla sınıfları. Bkz: [genel bakış, Bildirimcileri](../cpp/overview-of-declarators.md) daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Sınıflar hakkında daha fazla bilgi için genel olarak, aşağıdaki konulardan birine bakın:

- [struct](../cpp/struct-cpp.md)

- [birleşim](../cpp/unions.md)

- [__multiple_inheritance](../cpp/inheritance-keywords.md)

- [__single_inheritance](../cpp/inheritance-keywords.md)

- [__virtual_inheritance](../cpp/inheritance-keywords.md)

Bilgi yönetilen sınıflar ve yapılar C + +/ CLI ve C + +/ CX, bkz: [sınıflar ve yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)