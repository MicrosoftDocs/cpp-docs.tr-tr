---
title: Numaralandırmalar [C++]
ms.date: 06/01/2018
f1_keywords:
- enum_cpp
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
ms.openlocfilehash: d4511ed7d09ff280d01214a2a177148956580ee5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221620"
---
# <a name="enumerations-c"></a>Numaralandırmalar [C++]

Sabit listesi, Numaralandırıcılar olarak bilinen bir dizi adlandırılmış integral sabitinden oluşan Kullanıcı tanımlı türdür.

> [!NOTE]
> Bu makalede, **`enum`** C++ 11 ' de TANıTıLAN ISO standart C++ dil türü ve kapsamlı (veya kesin yazılmış) **sabit listesi sınıfı** türü ele alınmaktadır. C++/CLı ve C++/CX içindeki **genel enum sınıfı** veya **özel enum sınıfı** türleri hakkında daha fazla bilgi için bkz. [enum sınıfı](../extensions/enum-class-cpp-component-extensions.md).

## <a name="syntax"></a>Söz dizimi

```
// unscoped enum:
enum [identifier] [: type]
{enum-list};

// scoped enum:
enum [class|struct]
[identifier] [: type]
{enum-list};
```

```cpp
// Forward declaration of enumerations  (C++11):
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```

## <a name="parameters"></a>Parametreler

*Tanımlayıcısını*<br/>
Numaralandırmaya verilen tür adı.

*türüyle*<br/>
Numaralandırıcıların temel alınan türü; Tüm Numaralandırıcılar, temel alınan türe sahiptir. Herhangi bir tamsayı türü olabilir.

*Enum-Listele*<br/>
Numaralandırmadaki numaralandırıcıların virgülle ayrılmış listesi. Kapsamdaki her Numaralandırıcı veya değişken adı benzersiz olmalıdır. Ancak, değerler yinelenebilir. Kapsamlı olmayan bir numaralandırıcıda kapsam, çevreleyen kapsamdadır; kapsamlı bir numaralandırıcıda kapsam, *enum listesinin* kendisidir.  Kapsamlı bir sabit listesinde, liste boş olabilir ve yeni bir integral türünü tanımlar.

*sınıfı*<br/>
Bildirimde bu anahtar sözcüğü kullanarak, numaralandırmanın kapsama sahip olduğunu ve bir *tanımlayıcının* sağlanması gerektiğini belirtirsiniz. **`struct`** **`class`** Bu bağlamda anlamsal olarak eşdeğer olduklarından, yerine anahtar sözcüğünü de kullanabilirsiniz.

## <a name="enumerator-scope"></a>Numaralandırıcı kapsamı

Bir numaralandırma, adlandırılmış sabitler olarak temsil edilen ve ayrıca Numaralandırıcılar olarak adlandırılan bir değer aralığını açıklayan bağlamı sağlar. Özgün C ve C++ sabit listesi türlerinde, nitelenmemiş Numaralandırıcılar, numaralandırmanın bildirildiği kapsam boyunca görünür olur. Kapsamlı numaralandırmalar ' da, Numaralandırıcı adı sabit listesi türü adı ile nitelenmelidir. Aşağıdaki örnek, iki tür numaralandırmalar arasındaki bu temel farkı göstermektedir:

```cpp
namespace CardGame_Scoped
{
    enum class Suit { Diamonds, Hearts, Clubs, Spades };

    void PlayCard(Suit suit)
    {
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type
        { /*...*/}
    }
}

namespace CardGame_NonScoped
{
    enum Suit { Diamonds, Hearts, Clubs, Spades };

    void PlayCard(Suit suit)
    {
        if (suit == Clubs) // Enumerator is visible without qualification
        { /*...*/
        }
    }
}
```

Bir Numaralandırmadaki her ada, Numaralandırmadaki değerler sırasına karşılık gelen bir integral değer atanır. Varsayılan olarak, ilk değer 0 atanır, bir sonraki bir 1 atanır ve bu şekilde devam eder, ancak burada gösterildiği gibi, bir Numaralandırıcı değerini açıkça ayarlayabilirsiniz:

```cpp
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };
```

Numaralandırıcı `Diamonds` değere atanır `1` . Sonraki Numaralandırıcılar, açık bir değer verilmemişse, önceki Numaralandırıcı değerini ve bir değeri alın. Önceki örnekte, `Hearts` 2 değerine sahip olacaktır, `Clubs` 3 ve bu şekilde devam eder.

Her Numaralandırıcı bir sabit olarak değerlendirilir ve kapsam içinde **`enum`** tanımlanmış (kapsamı oluşturulmamış Numaralandırmalar için) veya **`enum`** kendisi içinde (kapsamlı Numaralandırmalar için) benzersiz bir ada sahip olmalıdır. Adlara verilen değerlerin benzersiz olması gerekmez. Örneğin, kapsamlı olmayan bir numaralandırma bildirimi `Suit` Bu ise:

```cpp
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };
```

Ardından,, `Diamonds` ve değerleri `Hearts` `Clubs` `Spades` sırasıyla 5, 6, 4 ve 5 ' tir. 5 ' in birden çok kez kullanıldığını unutmayın; Bu, amaçlanmasa bile izin verilir. Bu kurallar, kapsamlı Numaralandırmalar için aynıdır.

## <a name="casting-rules"></a>Atama kuralları

Kapsamlı olmayan Numaralandırma sabitleri örtük olarak öğesine dönüştürülebilir **`int`** , ancak hiçbir şekilde **`int`** hiçbir şekilde bir sabit listesi değerine dönüştürülemez. Aşağıdaki örnek, `hand` bir olmayan bir değer atamaya çalışırsanız ne olacağını gösterir `Suit` :

```cpp
int account_num = 135692;
Suit hand;
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
```

Bir atama, **`int`** kapsamı kapsamlı veya kapsamlı olmayan bir Numaralandırıcı dönüştürmek için gereklidir. Ancak, kapsamlı olmayan bir Numaralandırıcı 'yı bir dönüştürme olmadan bir tamsayı değerine yükseltebilirsiniz.

```cpp
int account_num = Hearts; //OK if Hearts is in a unscoped enum
```

Örtülü dönüştürmeleri bu şekilde kullanmak, istenmeyen yan etkilere neden olabilir. Kapsamlı olmayan numaralandırmalar ile ilişkili programlama hatalarının ortadan kaldırmaya yardımcı olmak için kapsamlı numaralandırma değerleri kesin olarak türdedir. Kapsamlı Numaralandırıcılar, enum türü adı (tanımlayıcı) ile nitelenmelidir ve aşağıdaki örnekte gösterildiği gibi örtük olarak dönüştürülemez:

```cpp
namespace ScopedEnumConversions
{
    enum class Suit { Diamonds, Hearts, Clubs, Spades };

    void AttemptConversions()
    {
        Suit hand;
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier
        hand = Suit::Clubs; //Correct.
        int account_num = 135692;
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!

        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'
        account_num = static_cast<int>(Suit::Hearts); // OK
    }
}
```

Satırın `hand = account_num;` , daha önce gösterildiği gibi kapsamlı numaralandırmalar ile oluşan hataya hala neden olduğuna dikkat edin. Açık bir tür dönüştürme ile buna izin verilir. Ancak, kapsamlı numaralandırmalar ile, sonraki ifadede yapılmaya çalışılan dönüştürmeye `account_num = Suit::Hearts;` artık açık bir atama yapılmaksızın izin verilmez.

## <a name="enums-with-no-enumerators"></a><a name="no_enumerators"></a>Numaralandırıcılar olmayan numaralandırmalar

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): açık bir temel alınan türe ve numaralandırıcılara sahip bir sabit listesi (normal veya kapsamlı) tanımlayarak, başka bir türe örtük dönüştürme olmayan yeni bir integral türü ortaya çıkarabilir. Yerleşik temel alınan türü yerine bu türü kullanarak, yanlışlıkla örtük dönüşümlerden kaynaklanan hafif hatalara karşı olası sorunları ortadan kaldırabilirsiniz.

```cpp
enum class byte : unsigned char { };
```

Yeni tür, temel alınan türün tam bir kopyasıdır ve dolayısıyla aynı çağırma kuralına sahiptir ve bu nedenle, herhangi bir performans cezası olmadan, ABR genelinde kullanılabileceği anlamına gelir. Tür değişkenleri doğrudan liste başlatma kullanılarak başlatıldığında atama gerekmez. Aşağıdaki örnek, çeşitli bağlamlarda Numaralandırıcılar olmadan Numaralandırmaların nasıl başlatılacağını göstermektedir:

```cpp
enum class byte : unsigned char { };

enum class E : int { };
E e1{ 0 };
E e2 = E{ 0 };

struct X
{
    E e{ 0 };
    X() : e{ 0 } { }
};

E* p = new E{ 0 };

void f(E e) {};

int main()
{
    f(E{ 0 });
    byte i{ 42 };
    byte j = byte{ 42 };

    // unsigned char c = j; // C2440: 'initializing': cannot convert from 'byte' to 'unsigned char'
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
