---
title: Sınıf Üyelerine Genel bakış
ms.date: 11/04/2016
helpviewer_keywords:
- members [C++], types of class members
- members [C++]
- class members [C++], types of
- class members
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
ms.openlocfilehash: 7847de072b2c0d5b95597e88f9ebf7e2ad63e180
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180959"
---
# <a name="class-member-overview"></a>Sınıf Üyelerine Genel bakış

Bir sınıf veya yapı, üyelerinden oluşur. Bir sınıfın yaptığı iş, kendi üye işlevleri tarafından gerçekleştirilir. Tuttuğu durum, veri üyelerinde saklanır. Üyelerin başlatılması oluşturucular tarafından yapılır ve bellek boşaltma ve kaynakların serbest bırakılması gibi temizleme işleri yok ediciler tarafından yapılır. C++ 11 ve sonrasında veri üyeleri, bildirim noktasında başlatılabilir (ve genellikle).

## <a name="kinds-of-class-members"></a>Sınıf üyesi türleri

Üye kategorilerinin tam listesi aşağıdaki gibidir:

- [Özel üye işlevleri](special-member-functions.md).

- [Üye Işlevlerine genel bakış](overview-of-member-functions.md).

- Yerleşik türler ve diğer Kullanıcı tanımlı türler dahil olmak üzere [veri üyeleri](static-members-cpp.md) .

- İşleçler

- [Iç Içe sınıf bildirimleri](nested-class-declarations.md) ve.)

- [Birleşimler](unions.md)

- [Numaralandırmalar](../cpp/enumerations-cpp.md).

- [Bit alanları](../cpp/cpp-bit-fields.md).

- [Arkadaşlar](../cpp/friend-cpp.md).

- [Diğer adlar ve tür tanımları](../cpp/aliases-and-typedefs-cpp.md).

    > [!NOTE]
    >  Sınıf bildirimi içinde bulunduğundan arkadaşlar yukarıdaki listeye dahil edilmiştir. Ancak sınıf kapsamı içinde olmadıklarından gerçek sınıf üyeleri değildirler.

## <a name="example-class-declaration"></a>Örnek sınıf bildirimi

Aşağıdaki örnekte basit bir sınıf bildirimi gösterilmektedir:

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

Bir sınıfın üyeleri üye listesinde bildirilmiştir. Bir sınıfın üye listesi, erişim belirticileri olarak bilinen anahtar sözcükler kullanılarak herhangi bir sayıda **özel**, **korunan** ve **genel** bölüme ayrılabilir.  İki nokta üst üste **:** erişim belirticisini izlemelidir.  Bu bölümlerin bitişik olması gerekmez, diğer bir deyişle, bu anahtar sözcüklerden biri üye listesinde birkaç kez görünebilir.  Sonraki erişim belirticisi veya kapanış ayracına kadar, anahtar sözcük tüm üyelerin erişimini belirler. Daha fazla bilgi için bkz. [üye Access ControlC++()](../cpp/member-access-control-cpp.md).

## <a name="static-members"></a>Statik üyeler

Bir veri üyesi statik olarak bildirilemez. Bu, sınıfın tüm nesnelerinin aynı kopyasına erişebileceği anlamına gelir. Üye işlevi statik olarak bildirilemez, bu durumda yalnızca sınıfın statik veri üyelerine erişebilir (ve *Bu* işaretçiye sahip değildir). Daha fazla bilgi için bkz. [statik veri üyeleri](../cpp/static-members-cpp.md).

## <a name="special-member-functions"></a>Özel üye işlevleri

Özel üye işlevleri, kaynak kodunuzda belirtmeyin derleyici tarafından otomatik olarak sağlanacak işlevlerdir.

1. Varsayılan kurucu

1. Kopya oluşturucu

1. **(C++ 11)** Oluşturucuyu Taşı

1. Kopya atama işleci

1. **(C++ 11)** Taşıma atama işleci

1. Yok edici

Daha fazla bilgi için bkz. [özel üye işlevleri](../cpp/special-member-functions.md).

## <a name="memberwise-initialization"></a>Memberwise başlatma

C++ 11 ve sonrasında, statik olmayan üye Bildirimciler başlatıcıları içerebilir.

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

Bir üyeye oluşturucuda bir değer atanırsa, bu değer üyenin bildirim noktasında başlatıldığı değerin üzerine yazar.

Belirli bir sınıf türünün tüm nesneleri için statik veri üyelerinin paylaşılan tek bir kopyası vardır. Statik veri üyeleri tanımlanmış olmalıdır ve dosya kapsamında başlatılabilir. (Statik veri üyeleri hakkında daha fazla bilgi için bkz. [statik veri üyeleri](../cpp/static-members-cpp.md).) Aşağıdaki örnek, bu başlatmanın nasıl gerçekleştirileceğini göstermektedir:

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
>  Tanımlanan `CanInit2` öğesinin `i` sınıfının bir üyesi olduğunu belirtmek için, sınıf adı `i`, `CanInit2` öğesinden önce gelmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
