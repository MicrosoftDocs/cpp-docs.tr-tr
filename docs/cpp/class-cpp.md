---
title: class (C++)
ms.date: 11/04/2016
f1_keywords:
- class_cpp
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
ms.openlocfilehash: 6475bc3703ce1bd7cf6103f4be8c12edc36e98b9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226014"
---
# <a name="class-c"></a>class (C++)

**`class`** Anahtar sözcüğü bir sınıf türü bildirir veya bir sınıf türünün nesnesini tanımlar.

## <a name="syntax"></a>Söz dizimi

```
[template-spec]
class [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[ class ] tag declarators;
```

#### <a name="parameters"></a>Parametreler

*Şablon-spec*<br/>
İsteğe bağlı şablon belirtimleri. Daha fazla bilgi için bkz. [Şablonlar](templates-cpp.md).

*sınıfı*<br/>
**`class`** Anahtar sözcüğü.

*MS-decl-spec*<br/>
İsteğe bağlı depolama sınıfı belirtimi. Daha fazla bilgi için [__declspec](../cpp/declspec.md) anahtar sözcüğüne bakın.

*Etiket*<br/>
Sınıfa verilen tür adı. Etiketi, sınıfının kapsamı içinde ayrılmış bir sözcük haline gelir. Etiket isteğe bağlıdır. Atlanırsa, anonim bir sınıf tanımlanmıştır. Daha fazla bilgi için bkz. [anonim sınıf türleri](../cpp/anonymous-class-types.md).

*temel liste*<br/>
Bu sınıfın üyelerinin türetileceğini sınıfların veya yapıların isteğe bağlı listesi. Daha fazla bilgi için bkz. [temel sınıflar](../cpp/base-classes.md) . Her temel sınıf veya yapı adı öncesinde bir erişim belirticisi ([genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md)) ve [sanal](../cpp/virtual-cpp.md) anahtar sözcük olabilir. Daha fazla bilgi için [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) içindeki üye erişimi tablosuna bakın.

*üye listesi*<br/>
Sınıf üyeleri listesi. Daha fazla bilgi için [sınıf üyesine genel bakış](../cpp/class-member-overview.md) bölümüne bakın.

*Bildirimciler*<br/>
Sınıf türünün bir veya daha fazla örneğinin adlarını belirten bildirimci listesi. Sınıfın tüm veri üyeleri ise, Bildirimciler başlatıcı listeleri içerebilir **`public`** . Bu yapılar, veri üyeleri varsayılan olarak sınıflardan farklı olan yapılarda daha yaygındır **`public`** . Daha fazla bilgi için bkz. [Bildirimcilerin genel bakış](../cpp/overview-of-declarators.md) .

## <a name="remarks"></a>Açıklamalar

Genel olarak sınıflar hakkında daha fazla bilgi için aşağıdaki konulardan birine bakın:

- [sýný](../cpp/struct-cpp.md)

- [birleşim](../cpp/unions.md)

- [__multiple_inheritance](../cpp/inheritance-keywords.md)

- [__single_inheritance](../cpp/inheritance-keywords.md)

- [__virtual_inheritance](../cpp/inheritance-keywords.md)

C++/CLı ve C++/CX içindeki yönetilen sınıflar ve yapılar hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)

## <a name="example"></a>Örnek

```cpp
// class.cpp
// compile with: /EHsc
// Example of the class keyword
// Exhibits polymorphism/virtual functions.

#include <iostream>
#include <string>
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

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Sınıflar ve yapılar](../cpp/classes-and-structs-cpp.md)
