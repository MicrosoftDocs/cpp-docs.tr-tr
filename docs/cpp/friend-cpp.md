---
description: 'Daha fazla bilgi edinin: arkadaş (C++)'
title: friend (C++)
ms.date: 07/15/2019
f1_keywords:
- friend_cpp
helpviewer_keywords:
- member access, from friend functions
- friend classes [C++]
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
ms.openlocfilehash: 6e25beb10a727d0dcefce15e96059b49c5661601
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337733"
---
# <a name="friend-c"></a>friend (C++)

Bazı durumlarda, bir sınıfın üyesi olmayan işlevlere veya ayrı bir sınıftaki tüm üyelere üye düzeyinde erişim vermek daha uygundur. Yalnızca bir sınıf uygulayıcısı kimlerin arkadaşlarını bildirebilirler. Bir işlev veya sınıf kendisini herhangi bir sınıfın arkadaş olarak bildiremez. Bir sınıf tanımında, **`friend`** sınıfınızın özel ve korumalı üyelerine erişim izni vermek için, anahtar sözcüğünü ve üye olmayan bir işlevin ya da başka bir sınıfın adını kullanın. Bir şablon tanımında, bir tür parametresi arkadaş olarak bildirilebilecek.

## <a name="syntax"></a>Syntax

```
class friend F
friend F;
```

## <a name="friend-declarations"></a>Arkadaş bildirimleri

Daha önce bildirilmemiş bir arkadaş işlev bildirirseniz, bu işlev kapsayan sınıf olmayan kapsama aktarılabilir.

Arkadaş bildiriminde belirtilen işlevler, anahtar sözcüğü kullanılarak bildirilenler gibi değerlendirilir **`extern`** . Daha fazla bilgi için bkz. [extern](extern-cpp.md).

Genel kapsama sahip işlevler, prototiplerinden önce arkadaş olarak bildirilebilecek olsa da, üye işlevleri, kendi sınıf bildiriminin görünüşünün önünde arkadaş olarak bildirilemez. Aşağıdaki kod neden başarısız olduğunu gösterir:

```cpp
class ForwardDeclared;   // Class name is known.
class HasFriends
{
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected
};
```

Yukarıdaki örnek, sınıf adını `ForwardDeclared` kapsama olarak girer, ancak tüm bildirimi — özellikle, işlevi bildiren bölüm `IsAFriend` — bilinmez. Bu nedenle, **`friend`** sınıftaki bildirim `HasFriends` bir hata oluşturur.

C++ 11 ' den başlayarak, bir sınıf için iki arkadaş bildirimi biçimi vardır:

```cpp
friend class F;
friend F;
```

İlk form, en içteki ad alanında bu ada göre mevcut bir sınıf bulunamazsa yeni bir F sınıfı tanıtır. **C++ 11**: ikinci form yeni bir sınıf sunmaz; sınıf zaten bildirildiği zaman kullanılabilir ve bir şablon türü parametresi ya da bir typedef olarak bir typedef bildirirken kullanılması gerekir.

`class friend F`Başvurulan tür henüz bildirilmemiş olduğunda kullanın:

```cpp
namespace NS
{
    class M
    {
        class friend F;  // Introduces F but doesn't define it
    };
}
```

```cpp
namespace NS
{
    class M
    {
        friend F; // error C2433: 'NS::F': 'friend' not permitted on data declarations
    };
}
```

Aşağıdaki örnekte, `friend F` `F` NS kapsamı dışında belirtilen sınıfa başvurur.

```cpp
class F {};
namespace NS
{
    class M
    {
        friend F;  // OK
    };
}
```

Bir `friend F` şablon parametresini arkadaş olarak bildirmek için kullanın:

```cpp
template <typename T>
class my_class
{
    friend T;
    //...
};
```

`friend F`Bir typedef öğesini arkadaş olarak bildirmek için kullanın:

```cpp
class Foo {};
typedef Foo F;

class G
{
    friend F; // OK
    friend class F // Error C2371 -- redefinition
};
```

Bir diğerinin arkadaşından oluşan iki sınıf bildirmek için ikinci sınıfın tamamı ilk sınıfın bir arkadaşınız olarak belirtilmelidir. Bu kısıtlamanın nedeni, derleyicinin tek tek arkadaş işlevlerini yalnızca ikinci sınıfın bildirildiği noktada bildirmek için yeterli bilgiye sahip olmasının nedenidir.

> [!NOTE]
> İkinci sınıfın tamamı ilk sınıfa bir arkadaşınız olmalıdır, ancak ilk sınıftaki işlevlerin ikinci sınıfın arkadaşları olacağını seçebilirsiniz.

## <a name="friend-functions"></a>arkadaş işlevleri

**`friend`** İşlev, bir sınıfın üyesi olmayan ancak sınıfın özel ve korunan üyelerine erişimi olan bir işlevdir. Arkadaş işlevleri sınıf üyeleri olarak kabul edilmez; Bunlar, özel erişim ayrıcalıkları verilen normal dış işlevlerdir. Arkadaşlar, sınıfın kapsamında değildir ve üye seçim işleçleri (**.** ve- **>** ) başka bir sınıfın üyesi olmadıkları müddetçe. Bir **`friend`** işlev, erişim veren sınıf tarafından bildirilmiştir. **`friend`** Bildirim, sınıf bildiriminde herhangi bir yere yerleştirilebilir. Erişim denetimi anahtar sözcüklerinden etkilenmez.

Aşağıdaki örnek `Point` , bir sınıfı ve bir Friend işlevini gösterir `ChangePrivate` . **`friend`** İşlevin `Point` parametre olarak aldığı nesnenin özel veri üyesine erişimi vardır.

```cpp
// friend_functions.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class Point
{
    friend void ChangePrivate( Point & );
public:
    Point( void ) : m_i(0) {}
    void PrintPrivate( void ){cout << m_i << endl; }

private:
    int m_i;
};

void ChangePrivate ( Point &i ) { i.m_i++; }

int main()
{
   Point sPoint;
   sPoint.PrintPrivate();
   ChangePrivate(sPoint);
   sPoint.PrintPrivate();
// Output: 0
           1
}
```

## <a name="class-members-as-friends"></a>Arkadaş olarak sınıf üyeleri

Sınıf üyesi işlevleri, diğer sınıflarda arkadaş olarak bildirilemez. Aşağıdaki örneği inceleyin:

```cpp
// classes_as_friends1.cpp
// compile with: /c
class B;

class A {
public:
   int Func1( B& b );

private:
   int Func2( B& b );
};

class B {
private:
   int _b;

   // A::Func1 is a friend function to class B
   // so A::Func1 has access to all members of B
   friend int A::Func1( B& );
};

int A::Func1( B& b ) { return b._b; }   // OK
int A::Func2( B& b ) { return b._b; }   // C2248
```

Önceki örnekte, sınıfına yalnızca işleve `A::Func1( B& )` arkadaş erişimi verilir `B` . Bu nedenle, özel üyeye erişim, `_b` `Func1` sınıfında değil, sınıfının içinde doğrudur `A` `Func2` .

Bir sınıf, **`friend`** tüm üye işlevleri bir sınıfın arkadaş işlevleri olan, yani üye işlevleri diğer sınıfın özel ve korunan üyelerine erişimi olan bir sınıftır. **`friend`** Sınıftaki bildirimin olduğunu varsayalım `B` :

```cpp
friend class A;
```

Bu durumda, sınıftaki tüm üye işlevlerine, `A` sınıfa arkadaş erişimi verilirdi `B` . Aşağıdaki kod, bir arkadaş sınıfının örneğidir:

```cpp
// classes_as_friends2.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class YourClass {
friend class YourOtherClass;  // Declare a friend class
public:
   YourClass() : topSecret(0){}
   void printMember() { cout << topSecret << endl; }
private:
   int topSecret;
};

class YourOtherClass {
public:
   void change( YourClass& yc, int x ){yc.topSecret = x;}
};

int main() {
   YourClass yc1;
   YourOtherClass yoc1;
   yc1.printMember();
   yoc1.change( yc1, 5 );
   yc1.printMember();
}
```

Bu şekilde açıkça belirtilmediği sürece, arkadaşlık karşılıklı değildir. Yukarıdaki örnekte, öğesinin üye işlevleri `YourClass` özel üyelerine erişemez `YourOtherClass` .

Yönetilen bir türün (C++/CLı ' da) arkadaş işlevleri, arkadaş sınıfları veya arkadaş arabirimleri olamaz.

Arkadaşlık devralınmaz, yani sınıfından türetilen sınıfların `YourOtherClass` özel üyelerine erişemeyeceği anlamına gelir `YourClass` . Arkadaşlık geçişli değildir, bu nedenle arkadaş olan sınıflar `YourOtherClass` `YourClass` Özel üyelere erişemez.

Aşağıdaki şekilde dört sınıf bildirimi gösterilmektedir: `Base` , `Derived` , `aFriend` , ve `anotherFriend` . Yalnızca sınıfının `aFriend` özel üyelerine `Base` (ve herhangi bir üyeye devralınmış olabilir) doğrudan erişimi vardır `Base` .

![Arkadaş ilişkisinin etkileri](../cpp/media/vc38v41.gif "Arkadaş ilişkisinin etkileri") <br/>
Arkadaş ilişkisinin etkileri

## <a name="inline-friend-definitions"></a>Satır içi arkadaş tanımları

Friend işlevleri, sınıf bildirimlerinin içinde tanımlanabilir (bir işlev gövdesi olarak verilebilir). Bu işlevler, satır içi işlevlerdir ve üye satır içi işlevleri gibi, tüm sınıf üyeleri görüldükten hemen sonra tanımlanmış gibi davranırlar, ancak bu durum sınıf kapsamı (sınıf bildiriminin sonu) kapatılmadan önce gerçekleşir. Sınıf bildirimlerinde tanımlanan arkadaş işlevleri kapsayan sınıfın kapsamdadır.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
