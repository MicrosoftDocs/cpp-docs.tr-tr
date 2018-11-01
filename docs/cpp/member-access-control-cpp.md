---
title: Üye Erişim Denetimi (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- access control [C++]
- member access [C++]
- member-access control [C++]
ms.assetid: 2d596bca-56ad-4277-94e1-ce3db45fa14a
ms.openlocfilehash: ee4e9d89878aab4be2e4daf45525f9e951d214f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611425"
---
# <a name="member-access-control-c"></a>Üye Erişim Denetimi (C++)

Erişim denetimleri birbirinden ayırmak etkinleştirme [genel](../cpp/public-cpp.md) bir sınıfın arabirim [özel](../cpp/private-cpp.md) uygulama ayrıntılarını ve [korumalı](../cpp/protected-cpp.md) tarafından yalnızca olan üyeleri kullanın türetilmiş sınıflar. Erişim belirticisi sonraki erişim belirticisi karşılaşılanaa kadar sonra bildirilen tüm üyeleri için geçerlidir.

```cpp
class Point
{
public:
    Point( int, int ) // Declare public constructor.;
    Point();// Declare public default constructor.
    int &x( int ); // Declare public accessor.
    int &y( int ); // Declare public accessor.

private:                 // Declare private state variables.
    int _x;
    int _y;

protected:      // Declare protected function for derived classes only.
    Point ToWindowCoords();
};
```

Varsayılan erişim **özel** bir sınıftaki ve **genel** yapı veya birleşim. Erişim tanımlayıcıları sınıfında olabilir herhangi sayıda herhangi bir sırada kullanılır. Sınıf türü nesneleri için depolama alanı ayırma uygulamaya bağlıdır, ancak üyelere, erişim belirticileri arasında sırayla daha yüksek bellek adresleri atanması garantidir.

## <a name="member-access-control"></a>Üye Erişim Denetimi

|Erişim türü|Açıklama|
|--------------------|-------------|
|[private](../cpp/private-cpp.md)|Olarak bildirilen sınıf üyeleri **özel** yalnızca üye işlevleri ve arkadaş sınıfı (sınıflar veya işlevler) tarafından kullanılabilir.|
|[protected](../cpp/protected-cpp.md)|Olarak bildirilen sınıf üyeleri **korumalı** üye işlevleri ve arkadaş sınıfı (sınıflar veya işlevler) tarafından kullanılabilir. Ayrıca, bunlar sınıftan türetilmiş sınıflar tarafından kullanılabilir.|
|[public](../cpp/public-cpp.md)|Olarak bildirilen sınıf üyeleri **genel** herhangi bir işlev tarafından kullanılabilir.|

Erişim denetimi, özel olarak kullanılmak üzere düşünülmemiş yollarla nesneleri kullanarak önlemeye yardımcı olur. Açık tür dönüştürmeleri (yayınları) gerçekleştirildiğinde bu koruma kaybolur.

> [!NOTE]
>  Erişim denetimi, tüm adları için eşit oranda geçerlidir: üye işlevleri, üye verilerini, iç içe geçmiş sınıflar ve numaralandırıcılar.

## <a name="access-control-in-derived-classes"></a>Türetilmiş sınıflarda erişim denetimi

İki etmen denetimi; türetilen bir sınıfta bir temel sınıfın hangi üyelerinin erişilebilir aynı faktörlerin devralınan üyeler türetilen sınıfta erişimi denetleme:

- Kullanarak temel sınıf türetilmiş bir sınıf olup olmadığını bildirir **genel** erişim belirticisi.

- Üye erişimi temel sınıfta nedir?

Aşağıdaki tabloda, bu faktörlerin ve temel sınıf üye erişimi belirleme arasındaki etkileşim gösterilmektedir.

### <a name="member-access-in-base-class"></a>Temel sınıftaki üye erişimi

|private|protected|Ortak|
|-------------|---------------|------------|
|Türetme erişim bakılmaksızın her zaman erişilemez|Özel türetme kullanırsanız, türetilmiş sınıf içinde özel|Özel türetme kullanırsanız, türetilmiş sınıf içinde özel|
||Korumalı türetme kullanırsanız, türetilmiş sınıf içinde korumalı|Korumalı türetme kullanırsanız, türetilmiş sınıf içinde korumalı|
||Türetilen sınıfta ortak türetme kullanıyorsanız, korumalı|Genel türetme kullanırsanız türetilmiş sınıftaki ortak|

Aşağıdaki örnek bunu göstermektedir:

```cpp
// access_specifiers_for_base_classes.cpp
class BaseClass
{
public:
    int PublicFunc(); // Declare a public member.
protected:
    int ProtectedFunc(); // Declare a protected member.
private:
    int PrivateFunc(); // Declare a private member.
};

// Declare two classes derived from BaseClass.
class DerivedClass1 : public BaseClass
{
    void foo()
    {
        PublicFunc();
        ProtectedFunc();
        PrivateFunc(); // function is inaccessible
    }
};

class DerivedClass2 : private BaseClass
{
    void foo()
    {
        PublicFunc();
        ProtectedFunc();
        PrivateFunc(); // function is inaccessible
    }
};

int main()
{
    DerivedClass1 derived_class1;
    DerivedClass2 derived_class2;
    derived_class1.PublicFunc();
    derived_class2.PublicFunc(); // function is inaccessible
}
```

İçinde `DerivedClass1`, üye işlevi `PublicFunc` genel bir üyesidir ve `ProtectedFunc` korumalı bir üye olduğundan `BaseClass` genel bir temel sınıf. `PrivateFunc` özel olduğu `BaseClass`, ve tüm türetilen sınıflar için erişilebilir değil.

İçinde `DerivedClass2`, İşlevler `PublicFunc` ve `ProtectedFunc` özel üyeler, çünkü olarak kabul edilir `BaseClass` özel bir temel sınıf. Yeniden `PrivateFunc` özel olduğu `BaseClass`, ve tüm türetilen sınıflar için erişilebilir değil.

Türetilmiş bir sınıf bir temel sınıf erişim belirticisi olmadan bildirebilirsiniz. Böyle bir durumda türetme türetilmiş sınıf bildiriminin kullanıyorsa, özel sayılır **sınıfı** anahtar sözcüğü. Türetme türetilmiş sınıf bildiriminin kullanıyorsa, genel olarak kabul edilir **yapı** anahtar sözcüğü. Örneğin, aşağıdaki kodu:

```cpp
class Derived : Base
...
```

eşdeğerdir:

```cpp
class Derived : private Base
...
```

Benzer şekilde, aşağıdaki kodu:

```cpp
struct Derived : Base
...
```

eşdeğerdir:

```cpp
struct Derived : public Base
...
```

Özel erişime sahip olacak şekilde bildirilebilirler üye işlevleri için erişilebilir olmadığına dikkat edin veya bu işlevler veya sınıflar kullanılarak bildirilir sürece türetilmiş sınıflar **arkadaş** temel sınıf bildiriminde.

A **birleşim** bir temel sınıf türüne sahip olamaz.

> [!NOTE]
>  Özel bir temel sınıf belirtirken onu açıkça kullanmanız önerilir **özel** kullanıcılar türetilmiş sınıfın üye erişimi anlamak için anahtar sözcüğü.

## <a name="access-control-and-static-members"></a>Erişim denetimi ve statik üyeler

Temel sınıf olarak belirttiğinizde **özel**, yalnızca statik olmayan üyeleri etkiler. Genel statik üyeler türetilmiş sınıflarda da erişilebilir. Ancak, işaretçiler, başvurular veya nesneleri kullanarak temel sınıf üyelerinin erişmek, aynı zamanda erişim denetiminin yeniden uygulandığı bir dönüştürme gerektirebilir. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// access_control.cpp
class Base
{
public:
    int Print();             // Nonstatic member.
    static int CountOf();    // Static member.
};

// Derived1 declares Base as a private base class.
class Derived1 : private Base
{
};
// Derived2 declares Derived1 as a public base class.
class Derived2 : public Derived1
{
    int ShowCount();    // Nonstatic member.
};
// Define ShowCount function for Derived2.
int Derived2::ShowCount()
{
   // Call static member function CountOf explicitly.
    int cCount = Base::CountOf();     // OK.

   // Call static member function CountOf using pointer.
    cCount = this->CountOf();  // C2247. Conversion of
                               //  Derived2 * to Base * not
                               //  permitted.
    return cCount;
}
```

Önceki kodda; erişim denetimi, bir `Derived2` işaretçisinden `Base` işaretçisine dönüşümü yasaklar. **Bu** işaretçi örtük olarak türüdür `Derived2 *`. Seçilecek `CountOf` işlevi **bu** türüne dönüştürülmesi gerekir `Base *`. `Base`, `Derived2` öğesinin özel dolaylı bir temel sınıfı olduğundan bu tür bir dönüştürmeye izin verilmez. Özel bir temel sınıf türüne dönüştürme yalnızca hemen türetilmiş sınıfların işaretçileri için kabul edilebilir. Bu nedenle, `Derived1 *` türünde işaretçiler `Base *` türüne dönüştürülebilir.

Kendisini seçmek üzere bir işaretçi, başvuru veya nesne kullanmadan `CountOf` işlevine açık şekilde çağrı yapmanın, herhangi bir dönüştürme yapılacağı anlamına gelmediğine dikkat edin. Bu nedenle, çağrıya izin verilir.

Türetilmiş bir sınıfın (`T`) üyeleri ve arkadaşları, bir `T` işaretçisini özel doğrudan bir `T` temel sınıfına dönüştürebilir.

## <a name="access-to-virtual-functions"></a>Sanal işlevlere erişim

Erişim denetimi uygulanan [sanal](../cpp/virtual-cpp.md) işlevler işlev çağrısını yapmak için kullanılan tür tarafından belirlenir. İşlev bildirimlerinin geçersiz kılınması, belirli bir türe yönelik erişim denetimini etkilemez. Örneğin:

```cpp
// access_to_virtual_functions.cpp
class VFuncBase
{
public:
    virtual int GetState() { return _state; }
protected:
    int _state;
};

class VFuncDerived : public VFuncBase
{
private:
    int GetState() { return _state; }
};

int main()
{
   VFuncDerived vfd;             // Object of derived type.
   VFuncBase *pvfb = &vfd;       // Pointer to base type.
   VFuncDerived *pvfd = &vfd;    // Pointer to derived type.
   int State;

   State = pvfb->GetState();     // GetState is public.
   State = pvfd->GetState();     // C2248 error expected; GetState is private;
}
```

Yukarıdaki örnekte, `GetState` türünün işaretçisi kullanılarak `VFuncBase` sanal işlevinin çağrılması, `VFuncDerived::GetState` öğesini çağırır ve `GetState` genel olarak kabul edilir. Bununla birlikte, `GetState` türünün işaretçisi kullanılarak `VFuncDerived` çağrılması, `GetState``VFuncDerived` sınıfında özel olarak bildirildiği için bir erişim denetimi ihlali oluşturur.

> [!CAUTION]
>  `GetState` sanal işlevi, `VFuncBase` temel sınıfının işaretçisi kullanılarak çağrılabilir. Bu, çağrılan işlevin bu işlevin temel sınıfı olduğu anlamına gelmez.

## <a name="access-control-with-multiple-inheritance"></a>Erişim denetimi ile birden çok devralma

Sanal temel sınıflar içeren birden çok devralma kafeslerinde, belirli bir ada birden fazla yolla ulaşılabilir. Bu farklı yollarda farklı erişim denetimi uygulanabileceği için derleyici en çok erişimi sağlayan yolu seçer. Aşağıdaki şekle bakın.

![Devralma grafiğinin yolları üzerinde erişim](../cpp/media/vc38v91.gif "vc38V91") devralma grafiğinin erişim boyunca yolları

Şekilde `VBase` sınıfında bildirilen bir ada her zaman `RightPath` sınıfıyla ulaşılır. `RightPath``VBase`'i özel olarak bildirirken, `LeftPath``VBase`'i genel bir temel sınıf olarak bildirdiği için sağdaki yol daha fazla erişilebilirdir.

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)
