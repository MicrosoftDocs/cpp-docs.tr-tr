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
ms.openlocfilehash: 2a1b3d33534887568c6a55e320e77e0a018cafff
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366330"
---
# <a name="enumerations-c"></a>Numaralandırmalar [C++]

Numaralandırma, numaralandırıcı olarak bilinen bir dizi adlandırılmış integral sabitinden oluşan kullanıcı tanımlı bir türdür.

> [!NOTE]
> Bu makale, ISO Standart C++ Dil **enum** türünü ve C++11'de tanıtılan kapsamlı (veya güçlü bir şekilde yazılan) **enum sınıfı** türünü kapsar. C++/CLI ve C++/CX'teki **ortak enum sınıfı** veya özel **enum sınıfı** türleri hakkında bilgi için [enum sınıfına](../extensions/enum-class-cpp-component-extensions.md)bakın.

## <a name="syntax"></a>Sözdizimi

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

*Tanımlayıcı*<br/>
Numaralandırmaya verilen tür adı.

*Türü*<br/>
Sayısalatörler in altında yatan tip; tüm sayısallaştırıcılar aynı altta yatan türe sahiptir. Herhangi bir integral türü olabilir.

*enum listesi*<br/>
Numaralandırmadaki numaralandırıcıların virgülden ayrılmış listesi. Kapsamdaki her sayısallaştırıcı veya değişken adı benzersiz olmalıdır. Ancak, değerler çoğaltılabilir. Kapsam dışı bir enumda, kapsam çevreleyen kapsamdır; kapsamlı bir enum, kapsam *enum-list* kendisidir.  Kapsamlı bir enumda, liste boş olabilir ve bu da yeni bir integral türünü tanımlar.

*sınıf*<br/>
Bildirimde bu anahtar kelimeyi kullanarak, enumun kapsamlı olduğunu ve bir *tanımlayıcının* sağlandığını belirtirsiniz. Bu bağlamda semantik olarak eşdeğer oldukları ndan, **sınıf**yerine **yapı** anahtar sözcüklerini de kullanabilirsiniz.

## <a name="enumerator-scope"></a>Sayısallaştırıcı kapsamı

Numaralandırma, adlandırılmış sabitler olarak temsil edilen ve numaralandırıcı olarak da adlandırılan bir dizi değeri tanımlamak için bağlam sağlar. Orijinal C ve C++ enum türlerinde, niteliksiz tümumeratörler enumun beyan edildiği kapsam boyunca görünür. Kapsamlı enumlarda, enumerator adı enum türü adı ile nitelikli olmalıdır. Aşağıdaki örnek, iki tür enum arasındaki temel farkı göstermektedir:

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

Numaralandırmadaki her ada, numaralandırmadaki değerler sırasına göre yerine karşılık gelen bir integral değer atanır. Varsayılan olarak, ilk değer 0 atanır, bir sonraki 1 atanır, ve benzeri, ancak açıkça burada gösterildiği gibi bir enumerator değerini ayarlayabilirsiniz:

```cpp
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };
```

Enumerator `Diamonds` değeri `1`atanır. Sonraki tümumeratörler, açık bir değer verilmezse, önceki sayısalatörü artı bir değerini alırsınız. Önceki örnekte, `Hearts` değeri 2 olurdu, `Clubs` 3 olurdu, ve benzeri.

Her enumerator sabit olarak kabul edilir ve **enum** tanımlanan kapsam içinde benzersiz bir adı olmalıdır (kapsamlı enumlar için) veya **enum** kendisi içinde (kapsamlı enums için). Adlara verilen değerlerin benzersiz olması gerekmez. Örneğin, kapsam dışı bir enum'un `Suit` bildirimi şuysa:

```cpp
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };
```

Daha sonra `Diamonds`, `Hearts` `Clubs`, `Spades` , ve sırasıyla 5, 6, 4 ve 5 değerleri. 5'in birden fazla kez kullanıldığına dikkat edin; bu amaçlanan olmasa bile izin verilir. Bu kurallar kapsamlı enumlar için aynıdır.

## <a name="casting-rules"></a>Döküm kuralları

Unscoped enum sabitleri dolaylı olarak **int**dönüştürülebilir, ancak bir **int** örtülü bir enum değerine dönüştürülemez. Aşağıdaki örnek, olmayan bir değer atamaya `hand` çalışırsanız ne `Suit`olacağını gösterir:

```cpp
int account_num = 135692;
Suit hand;
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
```

Bir **int'i** kapsamlı veya kapsamsız bir sayısalatöre dönüştürmek için bir döküm gereklidir. Ancak, bir döküm olmadan bir tamsayı değerine unscoped enumerator teşvik edebilirsiniz.

```cpp
int account_num = Hearts; //OK if Hearts is in a unscoped enum
```

Örtük dönüşümlerin bu şekilde kullanılması istenmeyen yan etkilere yol açabilir. Kapsamdışı enumlarla ilişkili programlama hatalarını ortadan kaldırmaya yardımcı olmak için kapsamlı enum değerleri güçlü bir şekilde yazılır. Kapsamlı sayısallaştırıcılar enum türü adı (tanımlayıcı) ile kalifiye edilmelidir ve aşağıdaki örnekte gösterildiği gibi örtülü olarak dönüştürülemez:

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

Satırın `hand = account_num;` daha önce gösterildiği gibi kapsam dışı enumlarla oluşan hataya neden olduğuna dikkat edin. Bu açık bir döküm ile izin verilir. Ancak, kapsamlı enums ile, bir sonraki `account_num = Suit::Hearts;`açıklamada dönüşüm girişimi, , artık açık bir döküm olmadan izin verilmez.

## <a name="enums-with-no-enumerators"></a><a name="no_enumerators"></a>No-lu noumerators ile Enumlar

**Visual Studio 2017 sürüm 15.3 ve sonrası** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir ): Açık bir temel türü olan ve hiçbir sayısallaştırıcı bulunmayan bir enum (normal veya kapsamlı) tanımlayarak, başka bir türe örtük dönüştürme olmayan yeni bir integral türünü tanıtabilirsiniz. Yerleşik altta yatan türü yerine bu türü kullanarak, yanlışlıkla örtülü dönüşümlerin neden olduğu ince hatalar için potansiyel ortadan kaldırabilirsiniz.

```cpp
enum class byte : unsigned char { };
```

Yeni tür, altta yatan türün tam bir kopyasıdır ve bu nedenle aynı çağrı kuralına sahiptir, bu da herhangi bir performans cezası olmaksızın ABI'ler arasında kullanılabildiği anlamına gelir. Tür değişkenleri doğrudan liste başlatma kullanılarak başharfe sorulduğunda döküm gerekmez. Aşağıdaki örnek, çeşitli bağlamlarda enumeratör olmadan enums nasıl başharfgösterilir gösterir:

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

[C Numaralandırma Bildirimleri](../c-language/c-enumeration-declarations.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
