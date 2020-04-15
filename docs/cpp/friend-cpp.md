---
title: friend (C++)
ms.date: 07/15/2019
f1_keywords:
- friend_cpp
helpviewer_keywords:
- member access, from friend functions
- friend classes [C++]
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
ms.openlocfilehash: 20116674feffaa5b4bbddf707dd3a4d0c1d9ad98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364439"
---
# <a name="friend-c"></a>friend (C++)

Bazı durumlarda, bir sınıfın üyesi olmayan işlevlere veya ayrı bir sınıftaki tüm üyelere üye düzeyinde erişim sağlamak daha uygundur. Yalnızca sınıf uygulayıcısı arkadaşlarının kim olduğunu bildirebilir. Bir işlev veya sınıf kendisini herhangi bir sınıfın arkadaşı olarak beyan edemez. Sınıf tanımında, **arkadaşınızın** anahtar sözcük ve üye olmayan bir işlevin veya başka bir sınıfın adını kullanarak sınıfınözel ve korumalı üyelerine erişim hakkı tanıyın. Şablon tanımında, bir tür parametresi arkadaş olarak ilan edilebilir.

## <a name="syntax"></a>Sözdizimi

```
class friend F
friend F;
```

## <a name="friend-declarations"></a>Arkadaş bildirimleri

Daha önce bildirilmemiş bir arkadaş işlevini bildirirseniz, bu işlev bir alandaki sınıf dışı kapsama dışa aktarılır.

Arkadaş bildiriminde bildirilen **işlevler, extern** anahtar sözcüğü kullanılarak bildirilmiş gibi değerlendirilir. Daha fazla bilgi için [extern'](extern-cpp.md)e bakın.

Genel kapsama sahip işlevler prototiplerinden önce arkadaş olarak bildirilebilse de, üye işlevler tam sınıf bildirimi nin ortaya çıkmasından önce arkadaş olarak bildirilemez. Aşağıdaki kod, bunun neden başarısız olduğunu gösterir:

```cpp
class ForwardDeclared;   // Class name is known.
class HasFriends
{
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected
};
```

Önceki örnek sınıf adını `ForwardDeclared` kapsamına girer, ancak tam bildirim -özellikle işlevi `IsAFriend` bildiren kısım- bilinmemektedir. Bu nedenle, sınıfta `HasFriends` **arkadaş** bildirimi bir hata oluşturur.

C++11'den başlayarak, bir sınıf için iki arkadaş bildirimi biçimi vardır:

```cpp
friend class F;
friend F;
```

İlk form, en içteki ad alanında bu ada göre varolan bir sınıf bulunamazsa yeni bir F sınıfı sunar. **C++11**: İkinci form yeni bir sınıf getirmez; sınıf zaten bildirilmişse kullanılabilir ve şablon türü parametresi veya bir yazı tipi arkadaş olarak bildirilirken kullanılmalıdır.

Başvurulan tür henüz bildirilmemişse kullanın: `class friend F`

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

Aşağıdaki örnekte, `friend F` NS `F` kapsamı dışında bildirilen sınıfa başvurur.

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

Şablon `friend F` parametresini arkadaş olarak bildirmek için kullanın:

```cpp
template <typename T>
class my_class
{
    friend T;
    //...
};
```

Bir `friend F` typedef'i arkadaş olarak bildirmek için kullanın:

```cpp
class Foo {};
typedef Foo F;

class G
{
    friend F; // OK
    friend class F // Error C2371 -- redefinition
};
```

Birbirinin arkadaşı olan iki sınıfı bildirmek için, ikinci sınıfın tamamının birinci sınıfın arkadaşı olarak belirtilmesi gerekir. Bu kısıtlamanın nedeni, derleyicinin yalnızca ikinci sınıfın beyan edildiği noktada tek tek arkadaş işlevlerini bildirmek için yeterli bilgiye sahip olmasıdır.

> [!NOTE]
> Tüm ikinci sınıf birinci sınıf için bir arkadaş olması gerekir, birinci sınıfta hangi işlevleri ikinci sınıfın arkadaşları olacağını seçebilirsiniz.

## <a name="friend-functions"></a>arkadaş işlevleri

**Arkadaş** işlevi, sınıfın üyesi olmayan ancak sınıfın özel ve korumalı üyelerine erişimi olan bir işlevdir. Arkadaş işlevleri sınıf üyesi olarak kabul edilmez; bunlar özel erişim ayrıcalıkları verilen normal dış işlevlerdir. Arkadaşlar sınıfın kapsamında değildir ve üye seçim işleçleri kullanılarak çağrılmaz (**.** ve**>**- ) başka bir sınıfın üyesi olmadıkça. Bir **arkadaş** işlevi erişim veren sınıf tarafından bildirilir. **Arkadaş** bildirimi sınıf bildiriminde herhangi bir yere yerleştirilebilir. Erişim denetimi anahtar kelimelerden etkilenmez.

Aşağıdaki örnekte `Point` bir sınıf ve `ChangePrivate`bir arkadaş işlevi gösterir. **Arkadaş** işlevi, parametre olarak aldığı `Point` nesnenin özel veri üyesine erişebilir.

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

Sınıf üye işlevleri diğer sınıflarda arkadaş olarak bildirilebilir. Aşağıdaki örneği inceleyin:

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

Önceki örnekte, yalnızca işlev `A::Func1( B& )` sınıfa `B`arkadaş erişimi verilir. Bu nedenle, özel `_b` üyeye `Func1` erişim `A` sınıfta doğrudur, ancak 'da `Func2`değil.

Sınıf, `friend` üye işlevleri bir sınıfın arkadaş işlevleri olan, yani üye işlevleri diğer sınıfın özel ve korumalı üyelerine erişimi olan bir sınıftır. Sınıftaki `friend` `B` bildirimin şöyle olduğunu varsayalım:

```cpp
friend class A;
```

Bu durumda, sınıftaki `A` tüm üye işlevlere sınıfa `B`arkadaş erişimi verilirdi. Aşağıdaki kod bir arkadaş sınıfına örnektir:

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

Dostluk açıkça belirtilmedikçe karşılıklı değildir. Yukarıdaki örnekte, üye `YourClass` işlevleri özel üyeleri `YourOtherClass`erişemez.

Yönetilen bir tür (C++/CLI'de) arkadaş işlevleri, arkadaş sınıfları veya arkadaş arabirimleri olamaz.

Arkadaşlık kalıtsal değildir, yani türetilen `YourOtherClass` sınıflar `YourClass`özel üyelere erişemez. Arkadaşlık geçişli değildir, bu yüzden arkadaş `YourOtherClass` olan `YourClass`sınıflar özel üyelere erişemezler.

Aşağıdaki şekil dört sınıf bildirimleri `Derived` `aFriend`gösterir: `anotherFriend` `Base`, , ve . Yalnızca `aFriend` sınıfın özel üyelerine `Base` (ve herhangi bir `Base` üyenin devralmış olabileceği) doğrudan erişimi vardır.

![Arkadaş ilişkisinin etkileri](../cpp/media/vc38v41.gif "Arkadaş ilişkisinin etkileri") <br/>
Arkadaş ilişkisinin etkileri

## <a name="inline-friend-definitions"></a>Satır satırlı arkadaş tanımları

Arkadaş işlevleri sınıf bildirimleri içinde tanımlanabilir (bir işlev gövdesi verilir). Bu işlevler, satır içi işlevlerdir ve üye satır içi işlevleri gibi, tüm sınıf üyeleri görüldükten hemen sonra tanımlanmış gibi davranırlar, ancak bu durum sınıf kapsamı (sınıf bildiriminin sonu) kapatılmadan önce gerçekleşir. Sınıf bildirimleri içinde tanımlanan arkadaş işlevleri çevreleyen sınıfın kapsamı içindedir.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
