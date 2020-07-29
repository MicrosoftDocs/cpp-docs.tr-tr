---
title: Üye Erişim Denetimi (C++)
ms.date: 11/19/2018
helpviewer_keywords:
- access control [C++]
- member access [C++]
- member-access control [C++]
ms.assetid: 2d596bca-56ad-4277-94e1-ce3db45fa14a
ms.openlocfilehash: de775c511701cd0b7cf923f47e33723b30a966e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186977"
---
# <a name="member-access-control-c"></a>Üye Erişim Denetimi (C++)

Erişim denetimleri [özel](../cpp/private-cpp.md) uygulama ayrıntılarından ve yalnızca türetilmiş sınıflar tarafından kullanılan [korumalı](../cpp/protected-cpp.md) üyelerden bir sınıfın [genel](../cpp/public-cpp.md) arabirimini ayırmanızı sağlar. Erişim belirticisi, sonraki erişim belirticisi ile karşılaşana kadar, bundan sonra belirtilen tüm Üyeler için geçerlidir.

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

Varsayılan erişim **`private`** bir sınıfta ve **`public`** bir yapıda veya birleşimde bulunur. Bir sınıftaki erişim belirticileri herhangi bir sırada herhangi bir sayıda kullanılabilir. Sınıf türü nesneleri için depolama alanı ayırma uygulamaya bağlıdır, ancak üyelere, erişim belirticileri arasında sırayla daha yüksek bellek adresleri atanması garantidir.

## <a name="member-access-control"></a>Üye Erişim Denetimi

|Erişim türü|Anlamı|
|--------------------|-------------|
|[özelleştirme](../cpp/private-cpp.md)|Olarak belirtilen sınıf üyeleri **`private`** , yalnızca sınıfın üye işlevleri ve arkadaşları (sınıflar veya işlevler) tarafından kullanılabilir.|
|[protected](../cpp/protected-cpp.md)|Olarak belirtilen sınıf üyeleri **`protected`** , sınıfının üye işlevleri ve arkadaşları (sınıflar veya işlevler) tarafından kullanılabilir. Ayrıca, sınıfından türetilmiş sınıflar tarafından kullanılabilirler.|
|[genel](../cpp/public-cpp.md)|Olarak belirtilen sınıf üyeleri **`public`** herhangi bir işlev tarafından kullanılabilir.|

Erişim denetimi, nesneleri kullanılması amaçlanmayan yöntemlerle kullanmanıza yardımcı olur. Bu koruma, açık tür dönüştürmeleri (yayınlar) gerçekleştirildiğinde kaybolur.

> [!NOTE]
> Erişim denetimi tüm adlara eşit olarak uygulanabilir: üye işlevleri, üye verileri, iç içe sınıflar ve Numaralandırıcılar.

## <a name="access-control-in-derived-classes"></a>Türetilmiş sınıflarda Access Control

Bir temel sınıfın hangi üyelerine türetilmiş bir sınıfta erişilebilir olduğu iki etken kontrol edilir; aynı faktörler türetilmiş sınıftaki devralınan üyelere erişimi denetler:

- Türetilmiş sınıfın, erişim belirticisini kullanarak temel sınıfı bildirmediği **`public`** .

- Üyenin erişimi temel sınıfta ne olur?

Aşağıdaki tabloda, bu faktörler arasındaki etkileşim ve temel sınıf üye erişiminin nasıl belirleneceği gösterilmektedir.

### <a name="member-access-in-base-class"></a>Taban sınıfta üye erişimi

|private|protected|Genel|
|-------------|---------------|------------|
|Türetme erişiminizden bağımsız olarak her zaman erişilemez|Özel türetme kullanırsanız türetilmiş sınıfta özel|Özel türetme kullanırsanız türetilmiş sınıfta özel|
||Korunan Türetmenin kullanıldığı türetilmiş sınıfta korunuyor|Korunan Türetmenin kullanıldığı türetilmiş sınıfta korunuyor|
||Ortak türetme kullanırsanız türetilmiş sınıfta korumalı|Ortak türetme kullanırsanız türetilmiş sınıfta ortak|

Aşağıdaki örnekte bu gösterilmektedir:

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

İçinde `DerivedClass1` , üye işlevi `PublicFunc` ortak bir üyedir ve bir `ProtectedFunc` `BaseClass` ortak temel sınıf olduğundan, korumalı bir üyedir. `PrivateFunc`özeldir `BaseClass` ve türetilmiş sınıfların hiçbirine erişemez.

İçinde `DerivedClass2` , ve özel `PublicFunc` `ProtectedFunc` bir temel sınıf olduğundan, işlevleri ve özel üye olarak değerlendirilir `BaseClass` . Ayrıca, `PrivateFunc` için özeldir `BaseClass` ve türetilmiş sınıfların hiçbirine erişemez.

Türetilmiş bir sınıfı, temel sınıf erişim belirticisi olmadan bildirebilirsiniz. Böyle bir durumda, türetilmiş sınıf bildirimi anahtar sözcüğünü kullanıyorsa türetme Private olarak kabul edilir **`class`** . Türetilmiş sınıf bildirimi anahtar sözcüğünü kullanıyorsa türetme ortak olarak kabul edilir **`struct`** . Örneğin, aşağıdaki kod:

```cpp
class Derived : Base
...
```

eşittir:

```cpp
class Derived : private Base
...
```

Benzer şekilde, aşağıdaki kod:

```cpp
struct Derived : Base
...
```

eşittir:

```cpp
struct Derived : public Base
...
```

Özel erişim sahibi olarak belirtilen üyelerin, bu işlevler veya sınıflar temel sınıftaki bildirim kullanılarak bildirilemediği sürece, işlevler veya türetilmiş sınıflar tarafından erişilemediğini unutmayın **`friend`** .

Bir **`union`** türün temel bir sınıfı olamaz.

> [!NOTE]
> Özel bir temel sınıf belirtirken, **`private`** türetilmiş sınıfın kullanıcılarının üye erişimini anlaması için anahtar sözcüğünün açıkça kullanılması önerilir.

## <a name="access-control-and-static-members"></a>Erişim denetimi ve statik Üyeler

Olarak bir temel sınıf belirttiğinizde **`private`** , yalnızca statik olmayan üyeleri etkiler. Genel statik üyeler türetilmiş sınıflarda da erişilebilir. Ancak, işaretçiler, başvurular veya nesneleri kullanarak temel sınıf üyelerinin erişmek, aynı zamanda erişim denetiminin yeniden uygulandığı bir dönüştürme gerektirebilir. Aşağıdaki örneği inceleyin:

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

Önceki kodda; erişim denetimi, bir `Derived2` işaretçisinden `Base` işaretçisine dönüşümü yasaklar. **`this`** İşaretçi örtülü olarak türündedir `Derived2 *` . İşlevi seçmek için `CountOf` , **`this`** türüne dönüştürülmesi gerekir `Base *` . `Base`, `Derived2` öğesinin özel dolaylı bir temel sınıfı olduğundan bu tür bir dönüştürmeye izin verilmez. Özel bir temel sınıf türüne dönüştürme yalnızca hemen türetilmiş sınıfların işaretçileri için kabul edilebilir. Bu nedenle, `Derived1 *` türünde işaretçiler `Base *` türüne dönüştürülebilir.

Kendisini seçmek üzere bir işaretçi, başvuru veya nesne kullanmadan `CountOf` işlevine açık şekilde çağrı yapmanın, herhangi bir dönüştürme yapılacağı anlamına gelmediğine dikkat edin. Bu nedenle, çağrıya izin verilir.

Türetilmiş bir sınıfın (`T`) üyeleri ve arkadaşları, bir `T` işaretçisini özel doğrudan bir `T` temel sınıfına dönüştürebilir.

## <a name="access-to-virtual-functions"></a>Sanal işlevlere erişim

[Sanal](../cpp/virtual-cpp.md) işlevlere uygulanan erişim denetimi, işlev çağrısını yapmak için kullanılan türe göre belirlenir. İşlev bildirimlerinin geçersiz kılınması, belirli bir türe yönelik erişim denetimini etkilemez. Örnek:

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
> `GetState` sanal işlevi, `VFuncBase` temel sınıfının işaretçisi kullanılarak çağrılabilir. Bu, çağrılan işlevin bu işlevin temel sınıfı olduğu anlamına gelmez.

## <a name="access-control-with-multiple-inheritance"></a>Birden çok Devralmada erişim denetimi

Sanal temel sınıflar içeren birden çok devralma kafeslerinde, belirli bir ada birden fazla yolla ulaşılabilir. Bu farklı yollarda farklı erişim denetimi uygulanabileceği için derleyici en çok erişimi sağlayan yolu seçer. Aşağıdaki şekle bakın.

![Devralma grafiğinin yolları üzerinde erişim](../cpp/media/vc38v91.gif "Devralma grafiğinin yolları üzerinde erişim") <br/>
Devralma grafiğinin yolları üzerinde erişim

Şekilde `VBase` sınıfında bildirilen bir ada her zaman `RightPath` sınıfıyla ulaşılır. `RightPath``VBase`'i özel olarak bildirirken, `LeftPath``VBase`'i genel bir temel sınıf olarak bildirdiği için sağdaki yol daha fazla erişilebilirdir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)
