---
title: friend (C++)
ms.date: 11/19/2018
f1_keywords:
- friend_cpp
helpviewer_keywords:
- member access, from friend functions
- friend classes [C++]
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
ms.openlocfilehash: 769720877cc58de530791b268811d7d01adad3e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154491"
---
# <a name="friend-c"></a>friend (C++)

Bazı durumlarda, bir sınıf üyesi olmayan işlevlere veya ayrı bir sınıftaki tüm üyeleri için üye düzeyi erişimi vermek daha uygundur. Yalnızca sınıf uygulayan kendi arkadaşlarınız olan bildirebilirsiniz. Bir işlev veya sınıf kendisi herhangi bir sınıfın arkadaş bildiremezsiniz. Bir sınıf tanımı içinde **arkadaş** anahtar sözcüğü ve üye olmayan işlev veya sınıfınız, özel ve korumalı üyelerine erişim vermek için başka bir sınıfın adı. Bir şablon tanımı içinde bir tür parametresi, bir arkadaş bildirilebilir.

## <a name="syntax"></a>Sözdizimi

```
class friend F
friend F;
```

## <a name="friend-declarations"></a>Arkadaş bildirimleri

Bu işlev, daha önce bildirilmemiş bir arkadaş işlev bildirirseniz, kapsayan nonclass kapsama dışarı aktarılır.

Bunlar kullanarak bildirilen gibi bir friend bildirimi içinde bildirilen işlevlerle edilir **extern** anahtar sözcüğü. Daha fazla bilgi için [extern](extern-cpp.md).

Genel kapsamlı işlevleri kendi prototipleri önce arkadaş olarak bildirilebilir olsa da, üye işlevleri kendi tam sınıf bildirimi görünümünü önce arkadaş olarak bildirilemez. Bu neden başarısız aşağıdaki kodun gösterdiği:

```cpp
class ForwardDeclared;   // Class name is known.
class HasFriends
{
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected
};
```

Yukarıdaki örnekte sınıf adını girer `ForwardDeclared` kapsamı, ancak tam bir bildirim içine — özellikle, bir işlev bildirir bölümü `IsAFriend` — bilinmiyor. Bu nedenle, **arkadaş** sınıf bildiriminde `HasFriends` bir hata oluşturur.

C ++ 11'de başlayarak, bir sınıfın arkadaş bildirimleri iki tür vardır:

```cpp
friend class F;
friend F;
```

En içteki ad alanında aynı adı taşıyan varolan bir sınıfı bulunduysa ilk formun yeni bir sınıf F sunar. **C ++ 11**: İkinci form, yeni bir sınıf sunmaz; sınıf zaten bildirilmiş ve bir şablon türü parametresine veya bir typedef arkadaş olarak bildirirken kullanılmalıdır kullanılabilir.

Kullanım `class friend F` zaman başvurulan tür değil henüz bildirildiği:

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

Aşağıdaki örnekte, `friend F` başvurduğu `F` NS kapsamı dışında bildirilen sınıf.

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

Kullanım `friend F` bir şablon parametresi bir arkadaş olarak bildirmek için:

```cpp
template <typename T>
class my_class
{
    friend T;
    //...
};
```

Kullanım `friend F` typedef arkadaş olarak bildirmek için:

```cpp
class Foo {};
typedef Foo F;

class G
{
    friend F; // OK
    friend class F // Error C2371 -- redefinition
};
```

Arkadaş birbirleriyle olan iki sınıf bildirmek için birinci sınıf bir arkadaş ikinci sınıfın tamamı belirtilmelidir. Bu kısıtlamanın nedeni, derleyicinin tek tek arkadaş işlevleri yalnızca ikinci sınıfı burada bildirildiği noktada bildirmek için yeterli bilgi sahip olur.

> [!NOTE]
>  Tüm saniye sınıfının arkadaşı ilk sınıf olmalıdır olsa da, hangi işlevleri ilk sınıf saniye sınıfının arkadaşların olacaktır seçebilirsiniz.

## <a name="friend-functions"></a>arkadaş işlevleri

A **arkadaş** işlev, bir işlev bir sınıfın üyesi değil ama sınıfın özel ve korumalı üyelerine erişebilir. Arkadaş işlevleri sınıf üyeleri olarak kabul edilmez; özel erişim ayrıcalıkları verilmiş normal dış işlevler değildirler. Arkadaşlar sınıf kapsamında değildir ve üye seçim işleçleri kullanarak çağrılır değil (**.** ve -**>**) başka bir sınıf üyesi olduğu sürece. A **arkadaş** erişim verme sınıfı tarafından bildirilen işlev. **Arkadaş** bildirimi yerleştirilebileceğini herhangi bir sınıf bildirimi içinde. Erişim denetimi anahtar sözcüklere göre etkilenmez.

Aşağıdaki örnekte gösterildiği bir `Point` sınıfı ve bir arkadaş işlev `ChangePrivate`. **Arkadaş** işlevi, özel veri üyesi erişimi olduğundan `Point` nesnesini parametre olarak alır.

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

## <a name="class-members-as-friends"></a>Arkadaş sınıfı üyeleri

Sınıf üyesi işlevleri, diğer sınıfların arkadaş olarak bildirilebilir. Aşağıdaki örnek göz önünde bulundurun:

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

Yukarıdaki örnekte, yalnızca işlev `A::Func1( B& )` sınıfına öğesine friend erişimi izni `B`. Bu nedenle özel bir üyesine erişmek `_b` doğru olduğu `Func1` sınıfın `A` fakat `Func2`.

A `friend` bir sınıfı olan tüm üye işlevleri, bir sınıfın arkadaş işlevleri, diğer bir deyişle, diğer sınıfın özel ve korumalı üyelerine erişimi, üye işlevleri vardır. Varsayalım `friend` sınıf bildiriminde `B` eklenmiştir:

```cpp
friend class A;
```

Bu durumda, tüm üye işlevler sınıfında `A` sınıfın arkadaş erişim verilmiş `B`. Aşağıdaki kod, bir arkadaş sınıfı örneğidir:

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

Bu nedenle açıkça belirtilmediği sürece karşılıklı Arkadaşlık değil. Yukarıdaki örnekte, üye işlevleri `YourClass` özel üyelerine erişemez `YourOtherClass`.

Yönetilen tür herhangi bir arkadaş işlevleri, arkadaş sınıfları veya arkadaş arabirimleri sahip olamaz.

Arkadaşlık değil devralınır, yani sınıfından türetilen sınıfların `YourOtherClass` erişemiyor `YourClass`ait özel üyeler. Arkadaşlık değil geçişli arkadaşların olmayan sınıflar için `YourOtherClass` erişemiyor `YourClass`ait özel üyeler.

Aşağıdaki şekilde dört sınıf bildirimi gösterilmektedir: `Base`, `Derived`, `aFriend`, ve `anotherFriend`. Yalnızca sınıf `aFriend` özel üyelerine doğrudan erişimi olan `Base` (ve tüm üyelerine `Base` devralınan).

![Arkadaş ilişki etkilerini](../cpp/media/vc38v41.gif "arkadaş ilişki etkileri") <br/>
Arkadaş ilişki etkileri

## <a name="inline-friend-definitions"></a>Satır içi arkadaş tanımları

Arkadaş işlevleri sınıf bildirimi içinde tanımlanabilir. Bu işlevler, satır içi işlevlerdir ve üye satır içi işlevleri gibi, tüm sınıf üyeleri görüldükten hemen sonra tanımlanmış gibi davranırlar, ancak bu durum sınıf kapsamı (sınıf bildiriminin sonu) kapatılmadan önce gerçekleşir.

Sınıf bildirimi içinde tanımlanan arkadaş işlevleri çevreleyen sınıf kapsamında dikkate alınmaz; dosya kapsamındadırlar.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)