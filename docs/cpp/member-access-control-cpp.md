---
title: Üye Erişim Denetimi (C++)
ms.date: 11/19/2018
helpviewer_keywords:
- access control [C++]
- member access [C++]
- member-access control [C++]
ms.assetid: 2d596bca-56ad-4277-94e1-ce3db45fa14a
ms.openlocfilehash: e8f62e82ebb7fcc18be5ac7d203df0fb46c9b635
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369854"
---
# <a name="member-access-control-c"></a>Üye Erişim Denetimi (C++)

Erişim denetimleri, bir sınıfın [ortak](../cpp/public-cpp.md) arabirimini [özel](../cpp/private-cpp.md) uygulama ayrıntılarından ve yalnızca türemiş sınıflar tarafından kullanılmak üzere [korunan](../cpp/protected-cpp.md) üyelerden ayırmanızı sağlar. Erişim belirtici, bir sonraki erişim belirticikarşılaşıncaya kadar ondan sonra bildirilen tüm üyeler için geçerlidir.

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

Varsayılan erişim bir sınıfta **özel,** bir yapı veya birleşimde **herkese açıktır.** Bir sınıftaki erişim belirteciler herhangi bir sırada herhangi bir sayıda kullanılabilir. Sınıf türü nesneleri için depolama alanı ayırma uygulamaya bağlıdır, ancak üyelere, erişim belirticileri arasında sırayla daha yüksek bellek adresleri atanması garantidir.

## <a name="member-access-control"></a>Üye Erişim Denetimi

|Erişim Türü|Anlamı|
|--------------------|-------------|
|[private](../cpp/private-cpp.md)|**Özel** olarak bildirilen sınıf üyeleri yalnızca sınıfın üye işlevleri ve arkadaşları (sınıflar veya işlevler) tarafından kullanılabilir.|
|[protected](../cpp/protected-cpp.md)|**Korumalı** olarak bildirilen sınıf üyeleri, sınıfın üye işlevleri ve arkadaşları (sınıflar veya işlevler) tarafından kullanılabilir. Ayrıca, sınıftan türetilen sınıflar tarafından kullanılabilir.|
|[public](../cpp/public-cpp.md)|**Genel** olarak bildirilen sınıf üyeleri herhangi bir işlev tarafından kullanılabilir.|

Erişim denetimi, nesneleri kullanılmak üzere tasarlanmadıkları şekilde kullanmanızı önlemeye yardımcı olur. Bu koruma, açık tür dönüşümleri (dökümler) yapıldığında kaybolur.

> [!NOTE]
> Erişim denetimi tüm adlar için eşit derecede geçerlidir: üye işlevler, üye verileri, iç içe sınıflar ve sayısallaştırıcılar.

## <a name="access-control-in-derived-classes"></a>Türemiş Sınıflarda Erişim Denetimi

Bir taban sınıfın hangi üyelerine türemiş bir sınıfta erişilebilir olduğunu denetlemeiki etken; bu aynı etkenler türemiş sınıfta devralınan üyelere erişimi denetler:

- Türemiş sınıfın **ortak** erişim belirtimi kullanarak taban sınıfı beyan edip etmediği.

- Üyeye erişimin taban sınıfta ne olduğu.

Aşağıdaki tabloda, bu etkenler arasındaki etkileşim ve taban sınıf üye erişiminin nasıl belirlenene yol açılabilir.

### <a name="member-access-in-base-class"></a>Taban Sınıfında Üye Erişimi

|private|protected|Genel|
|-------------|---------------|------------|
|Türetme erişimine bakılmaksızın her zaman erişilemez|Özel türetme kullanıyorsanız türemiş sınıfta özel|Özel türetme kullanıyorsanız türemiş sınıfta özel|
||Korumalı türev kullanıyorsanız türemiş sınıfta korumalı|Korumalı türev kullanıyorsanız türemiş sınıfta korumalı|
||Genel türetme kullanıyorsanız türemiş sınıfta korumalı|Genel türetme kullanıyorsanız türemiş sınıfta genel|

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

In, `DerivedClass1`üye `PublicFunc` işlev ortak bir `ProtectedFunc` üyedir ve `BaseClass` bir ortak taban sınıf olduğu için korunan bir üyedir. `PrivateFunc`özeldir `BaseClass`ve türetilmiş sınıflara erişilemez.

Özel `DerivedClass2`taban `PublicFunc` sınıf `ProtectedFunc` `BaseClass` olduğu için , işlevler ve özel üye olarak kabul edilir. Yine, `PrivateFunc` özel `BaseClass`, ve herhangi bir türemiş sınıflar için erişilemez.

Türemiş bir sınıfı taban sınıf erişim belirtimi olmadan bildirebilirsiniz. Türemiş sınıf bildirimi **sınıf** anahtar sözcüğü kullanıyorsa, türemiş türemiş özel olarak kabul edilir. Türemiş sınıf bildirimi **yapı** anahtar sözcüğü kullanıyorsa türetme genel olarak kabul edilir. Örneğin, aşağıdaki kod:

```cpp
class Derived : Base
...
```

eşdeğerdir:

```cpp
class Derived : private Base
...
```

Benzer şekilde, aşağıdaki kod:

```cpp
struct Derived : Base
...
```

eşdeğerdir:

```cpp
struct Derived : public Base
...
```

Özel erişime sahip olarak beyan edilen üyelerin, bu işlevler veya sınıflar taban sınıfta **arkadaş** bildirimi kullanılarak bildirilmedikçe işlevler veya türetilmiş sınıflar tarafından erişilemeyeceğini unutmayın.

**Birleşim** türünde taban sınıf olamaz.

> [!NOTE]
> Özel bir taban sınıf belirtirken, türemiş sınıfın kullanıcılarının üye erişimini anlamaları için **özel** anahtar sözcüğü açıkça kullanmanız tavsiye edilir.

## <a name="access-control-and-static-members"></a>Erişim denetimi ve statik üyeler

Bir taban sınıfı **özel**olarak belirttiğiniz zaman, yalnızca statik olmayan üyeleri etkiler. Genel statik üyeler türetilmiş sınıflarda da erişilebilir. Ancak, işaretçiler, başvurular veya nesneleri kullanarak temel sınıf üyelerinin erişmek, aynı zamanda erişim denetiminin yeniden uygulandığı bir dönüştürme gerektirebilir. Aşağıdaki örneği inceleyin:

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

Önceki kodda; erişim denetimi, bir `Derived2` işaretçisinden `Base` işaretçisine dönüşümü yasaklar. **Bu** işaretçi örtülü olarak `Derived2 *`türüdür. İşlevseçmek `CountOf` için **bu** türe `Base *`dönüştürülmelidir. `Base`, `Derived2` öğesinin özel dolaylı bir temel sınıfı olduğundan bu tür bir dönüştürmeye izin verilmez. Özel bir temel sınıf türüne dönüştürme yalnızca hemen türetilmiş sınıfların işaretçileri için kabul edilebilir. Bu nedenle, `Derived1 *` türünde işaretçiler `Base *` türüne dönüştürülebilir.

Kendisini seçmek üzere bir işaretçi, başvuru veya nesne kullanmadan `CountOf` işlevine açık şekilde çağrı yapmanın, herhangi bir dönüştürme yapılacağı anlamına gelmediğine dikkat edin. Bu nedenle, çağrıya izin verilir.

Türetilmiş bir sınıfın (`T`) üyeleri ve arkadaşları, bir `T` işaretçisini özel doğrudan bir `T` temel sınıfına dönüştürebilir.

## <a name="access-to-virtual-functions"></a>Sanal işlevlere erişim

[Sanal](../cpp/virtual-cpp.md) işlevlere uygulanan erişim denetimi, işlev çağrısı yapmak için kullanılan türe göre belirlenir. İşlev bildirimlerinin geçersiz kılınması, belirli bir türe yönelik erişim denetimini etkilemez. Örneğin:

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

## <a name="access-control-with-multiple-inheritance"></a>Birden çok devralma ile erişim denetimi

Sanal temel sınıflar içeren birden çok devralma kafeslerinde, belirli bir ada birden fazla yolla ulaşılabilir. Bu farklı yollarda farklı erişim denetimi uygulanabileceği için derleyici en çok erişimi sağlayan yolu seçer. Aşağıdaki şekle bakın.

![Devralma grafiğinin yolları boyunca erişim](../cpp/media/vc38v91.gif "Devralma grafiğinin yolları boyunca erişim") <br/>
Devralma grafiğinin yolları boyunca erişim

Şekilde `VBase` sınıfında bildirilen bir ada her zaman `RightPath` sınıfıyla ulaşılır. `RightPath``VBase`'i özel olarak bildirirken, `LeftPath``VBase`'i genel bir temel sınıf olarak bildirdiği için sağdaki yol daha fazla erişilebilirdir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)
