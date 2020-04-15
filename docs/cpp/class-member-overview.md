---
title: Sınıf Üyelerine Genel bakış
ms.date: 11/04/2016
helpviewer_keywords:
- members [C++], types of class members
- members [C++]
- class members [C++], types of
- class members
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
ms.openlocfilehash: cb978434707a9a7808b3388fc541ce4e0d996b0f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366673"
---
# <a name="class-member-overview"></a>Sınıf Üyelerine Genel bakış

Bir sınıf veya yapı, üyelerinden oluşur. Bir sınıfın yaptığı iş, üye işlevleri tarafından gerçekleştirilir. Koruduğu durum veri üyelerinde depolanır. Üyelerin başlatılması yapıcılar tarafından yapılır ve bellek serbest bırakılması ve kaynakların serbest bırakılması gibi temizleme çalışmaları yıkıcılar tarafından yapılır. C++11 ve sonraki durumlarda, veri üyeleri (ve genellikle olmalıdır) bildirim noktasında başharfe biçilebilir.

## <a name="kinds-of-class-members"></a>Sınıf üyeleri çeşitleri

Üye kategorilerinin tam listesi aşağıdaki gibidir:

- [Özel Üye Fonksiyonları](special-member-functions.md).

- [Üye Fonksiyonlar Genel Bakış](overview-of-member-functions.md).

- Yerleşik türleri ve diğer kullanıcı tanımlı türleri de dahil olmak üzere [veri üyeleri.](static-members-cpp.md)

- İşleçler

- [İç Içe Sınıf Bildirimleri](nested-class-declarations.md) ve.)

- [Birleşimler](unions.md)

- [Sayısallaştırmalar](../cpp/enumerations-cpp.md).

- [Bit alanları](../cpp/cpp-bit-fields.md).

- [Arkadaşlar](../cpp/friend-cpp.md).

- [Takma adlar ve typedefs](../cpp/aliases-and-typedefs-cpp.md).

    > [!NOTE]
    >  Sınıf bildirimi içinde bulunduğundan arkadaşlar yukarıdaki listeye dahil edilmiştir. Ancak sınıf kapsamı içinde olmadıklarından gerçek sınıf üyeleri değildirler.

## <a name="example-class-declaration"></a>Örnek sınıf bildirimi

Aşağıdaki örnekbasit bir sınıf bildirimini gösterir:

```cpp
// TestRun.h

class TestRun
{
    // Start member list.

    //The class interface accessible to all callers.
public:
    // Use compiler-generated default constructor:
    TestRun() = default;
    // Don't generate a copy constructor:
    TestRun(const TestRun&) = delete;
    TestRun(std::string name);
    void DoSomething();
    int Calculate(int a, double d);
    virtual ~TestRun();
    enum class State { Active, Suspended };

    // Accessible to this class and derived classes only.
protected:
    virtual void Initialize();
    virtual void Suspend();
    State GetState();

    // Accessible to this class only.
private:
    // Default brace-initialization of instance members:
    State _state{ State::Suspended };
    std::string _testName{ "" };
    int _index{ 0 };

    // Non-const static member:
    static int _instances;
    // End member list.
};

// Define and initialize static member.
int TestRun::_instances{ 0 };
```

## <a name="member-accessibility"></a>Üye erişilebilirliği

Bir sınıfın üyeleri üye listesinde ilan edilir. Bir sınıfın üye listesi, erişim belirteçleri olarak bilinen anahtar kelimeler kullanılarak herhangi bir sayıda **özel,** **korumalı** ve **ortak** bölüme ayrılabilir.  Bir iki nokta üst üste **:** erişim belirtici takip etmelidir.  Bu bölümlerin bitişik olması gerekmez, diğer bir deyişle, bu anahtar sözcüklerden biri üye listesinde birkaç kez görünebilir.  Sonraki erişim belirticisi veya kapanış ayracına kadar, anahtar sözcük tüm üyelerin erişimini belirler. Daha fazla bilgi için [Üye Erişim Denetimi (C++)](../cpp/member-access-control-cpp.md)'a bakın.

## <a name="static-members"></a>Statik üyeler

Bir veri üyesi statik olarak bildirilebilir, bu da sınıfın tüm nesnelerinin aynı kopyaya erişebileceği anlamına gelir. Bir üye işlev statik olarak bildirilebilir, bu durumda yalnızca sınıfın statik veri üyelerine erişebilir (ve *bu* işaretçisi yoktur). Daha fazla bilgi için Statik [Veri Üyeleri'ne](../cpp/static-members-cpp.md)bakın.

## <a name="special-member-functions"></a>Özel üye işlevleri

Özel üye işlevler, kaynak kodunuzda belirtmezseniz derleyici tarafından otomatik olarak sağlanan işlevlerdir.

1. Varsayılan kurucu

1. Kopya oluşturucu

1. **(C++11)** Taşı oluşturucu

1. Kopya atama işleci

1. **(C++11)** Atama işlecini taşı

1. Yok edici

Daha fazla bilgi için [Özel Üye Fonksiyonları'na](../cpp/special-member-functions.md)bakın.

## <a name="memberwise-initialization"></a>Memberwise başlatma

C++11 ve sonraki durumlarda statik olmayan üye bildirimciler baş harflerini içerebilir.

```cpp
class CanInit
{
public:
    long num {7};       // OK in C++11
    int k = 9;          // OK in C++11
    static int i = 9; // Error: must be defined and initialized
                      // outside of class declaration.

    // initializes num to 7 and k to 9
    CanInit(){}

    // overwrites original initialized value of num:
    CanInit(int val) : num(val) {}
};
int main()
{
}
```

Bir üyeye bir kurucuya bir değer atanmışsa, bu değer, üyenin bildirim noktasında başharfe basılan değerin üzerine yazar.

Belirli bir sınıf türünün tüm nesneleri için statik veri üyelerinin paylaşılan tek bir kopyası vardır. Statik veri üyeleri tanımlanmış olmalıdır ve dosya kapsamında başlatılabilir. (Statik veri üyeleri hakkında daha fazla bilgi için Statik [Veri Üyeleri'ne](../cpp/static-members-cpp.md)bakın.) Aşağıdaki örnek, bu başlatmaların nasıl gerçekleştirilini gösterir:

```cpp
// class_members2.cpp
class CanInit2
{
public:
    CanInit2() {} // Initializes num to 7 when new objects of type
                 //  CanInit are created.
    long     num {7};
    static int i;
    static int j;
};

// At file scope:

// i is defined at file scope and initialized to 15.
// The initializer is evaluated in the scope of CanInit.
int CanInit2::i = 15;

// The right side of the initializer is in the scope
// of the object being initialized
int CanInit2::j = i;
```

> [!NOTE]
> Tanımlanan `CanInit2` öğesinin `i` sınıfının bir üyesi olduğunu belirtmek için, sınıf adı `i`, `CanInit2` öğesinden önce gelmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
