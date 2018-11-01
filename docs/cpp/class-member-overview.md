---
title: Sınıf Üyelerine Genel bakış
ms.date: 11/04/2016
helpviewer_keywords:
- members [C++], types of class members
- members [C++]
- class members [C++], types of
- class members
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
ms.openlocfilehash: 8edfadefdacf94685952d31f2eaf83e8593eaef8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637924"
---
# <a name="class-member-overview"></a>Sınıf Üyelerine Genel bakış

Bir sınıf veya yapı üyelerine oluşur. Bir sınıf yaptığı işi kendi üye işlevleri tarafından gerçekleştirilir. Sakladığı durumu veri üyelerine depolanır. Oluşturucular ve bellek serbest bırakma gibi temizleme işini başlatma üyelerinin gerçekleştirilir ve kaynaklarını serbest yok ediciler tarafından gerçekleştirilir. C ++ 11 ve sonraki sürümlerinde, veri üyesi bildirildiği başlatılması kullanabilirsiniz ve genellikle gerekir.

## <a name="kinds-of-class-members"></a>Sınıf üyeleri türleri

Üye kategorileri tam listesini aşağıdaki gibidir:

- [Özel üye işlevleri](special-member-functions.md).

- [Üye işlevlerine genel bakış](overview-of-member-functions.md).

- [Veri üyeleri](static-members-cpp.md) dahil olmak üzere yerleşik türler ve diğer kullanıcı tanımlı türler.

- İşleçler

- [İç içe sınıf bildirimleri](nested-class-declarations.md) ve.)

- [Birleşimler](unions.md)

- [Numaralandırmalar](../cpp/enumerations-cpp.md).

- [Bit alanları](../cpp/cpp-bit-fields.md).

- [Arkadaş](../cpp/friend-cpp.md).

- [Diğer adlar ve tür tanımları](../cpp/aliases-and-typedefs-cpp.md).

    > [!NOTE]
    >  Sınıf bildirimi içinde bulunduğundan arkadaşlar yukarıdaki listeye dahil edilmiştir. Ancak sınıf kapsamı içinde olmadıklarından gerçek sınıf üyeleri değildirler.

## <a name="example-class-declaration"></a>Örnek sınıf bildirimi

Aşağıdaki örnek, bir basit sınıf bildirimi gösterilmektedir:

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

Bir sınıfın üyeleri, üye listesinde bildirilir. Bir sınıfın üye listesi herhangi bir sayıya bölünebilir **özel**, **korumalı** ve **genel** erişim belirticileri denen anahtar sözcükler kullanılarak bölümler.  Bir iki nokta üst üste **:** erişim belirticisinden gerekir.  Bu bölümlerin bitişik olması gerekmez, diğer bir deyişle, bu anahtar sözcüklerden biri üye listesinde birkaç kez görünebilir.  Sonraki erişim belirticisi veya kapanış ayracına kadar, anahtar sözcük tüm üyelerin erişimini belirler. Daha fazla bilgi için [üye erişim denetimi (C++)](../cpp/member-access-control-cpp.md).

## <a name="static-members"></a>Statik üyeler

Bir veri üyesinin statik olarak, sınıfın tüm nesneleri aynı kopyasını erişiminiz olduğu anlamına gelir bildirilebilir. Bir üye işlev bu durumda sınıfın statik veri üyeleri yalnızca erişebildiğinizi statik olarak bildirilebilir (ve hiçbir *bu* işaretçisi). Daha fazla bilgi için [statik veri üyeleri](../cpp/static-members-cpp.md).

## <a name="special-member-functions"></a>Özel üye işlevleri

Özel üye işlevleri, kaynak kodunuzda belirtmemeniz durumunda, derleyici tarafından otomatik olarak sağlanan işlevlerdir.

1. Varsayılan oluşturucu

1. Kopya oluşturucu

1. **(C ++ 11)**  Taşıma Oluşturucusu

1. Kopya atama işleci

1. **(C ++ 11)**  Taşıma atama işleci

1. Yok edici

Daha fazla bilgi için [özel üye işlevleri](../cpp/special-member-functions.md).

## <a name="memberwise-initialization"></a>Üye tabanlı başlatma

C ++ 11 ve sonraki sürümlerinde, statik olmayan üye bildirimcilerde başlatıcılar içerebilir.

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

Üye bir oluşturucuda bir değer atanırsa, bu değeri ile üyesi bildirildiği başlatıldı değer üzerine yazar.

Belirli bir sınıf türünün tüm nesneleri için statik veri üyelerinin paylaşılan tek bir kopyası vardır. Statik veri üyeleri tanımlanmış olmalıdır ve dosya kapsamında başlatılabilir. (Statik veri üyeleri hakkında daha fazla bilgi için bkz: [statik veri üyeleri](../cpp/static-members-cpp.md).) Aşağıdaki örnekte bu başlatmaların nasıl yapıldığı gösterilmektedir:

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