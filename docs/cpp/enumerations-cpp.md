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
ms.openlocfilehash: caec9ea7ac5482ff23b73676a3fd7b3d25ad293f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398946"
---
# <a name="enumerations-c"></a>Numaralandırmalar [C++]

Bir numaralandırma, numaralandırıcılar olarak bilinen adlandırılmış integral sabitleri kümesinden oluşan kullanıcı tanımlı bir tür ' dir.

> [!NOTE]
>  Bu makale ISO standardı C++ dili kapsamaktadır **enum** türü ve kapsamlı (veya türü kesin belirlenmiş) **sabit listesi sınıfı** C ++ 11'de kullanıma sunulan türü. Hakkında bilgi için **genel sabit listesi sınıfı** veya **özel enum sınıfı** türlerini C++/CLI ve C++/CX, bkz: [sabit listesi sınıfı](../extensions/enum-class-cpp-component-extensions.md).

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

*tanımlayıcı*<br/>
Numaralandırmaya verilen tür adı.

*type*<br/>
Numaralandırmaların temel türü; tüm sabit listelerinin arkasındaki tür aynıdır. Herhangi bir tamsayı türü olabilir.

*Numaralandırma listesi*<br/>
Sabit listesindeki numaralandırıcıların virgülle ayrılmış listesi. Her Numaralayıcı ya da değişken adı kapsamında benzersiz olmalıdır. Ancak, değerler çoğaltılabilir. Kapsamsız bir enum'da kapsam çevreleyen kapsamdır; kapsamlı bir enum'da kapsam olan *numaralandırma listesi* kendisi.  Kapsamlı bir enum'da listenin geçerli yeni bir integral türü tanımlayan boş olabilir.

*class*<br/>
Bu anahtar sözcüğü bildirimde kullanarak kapsamlı numaralandırma, belirttiğiniz ve *tanımlayıcı* sağlanmalıdır. Ayrıca **yapı** anahtar sözcüğü yerine **sınıfı**, bu bağlamda anlamsal olarak eşdeğer olarak.

## <a name="enumerator-scope"></a>Numaralandırıcı kapsamı

Bir numaralandırma sabitler gösterilir ve ayrıca numaralandırıcılar adıyla değer aralığını tanımlamak için bağlam sağlar. Özgün C ve C++ enum türlerinde, miktarı belirtilmemiş numaralandırıcılar enum bildirildiği kapsam boyunca görünürdür. Kapsamlı enum'larda, numaralandırıcı adı enum tür adı ile nitelenmelidir. Aşağıdaki örnek iki enum türü arasındaki bu temel farkı göstermektedir:

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

Numaralandırma içindeki her ada Numaralandırmadaki değerler sıralamasındaki konumuna karşılık gelen bir tamsayı değeri atanır. Varsayılan olarak, ilk değere 0 atanır, bir sonrakine 1 ve benzeri atanmış, ancak Numaralandırıcı değerini aşağıda gösterildiği gibi açıkça ayarlayabilirsiniz:

```cpp
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };
```

Numaralandırıcı `Diamonds` değeri atanır `1`. Sonraki numaralandırıcılar, açıkça bir değer verilmemişse yanı sıra bir önceki numaralandırıcıların değeri alır. Önceki örnekte, `Hearts` 2 değerine sahip `Clubs` 3 sahip ve benzeri.

Her Numaralayıcı sabit kabul edilir ve kapsam içinde benzersiz bir ad olmalıdır nerede **enum** (kapsamsız Enum'lar için) tanımlanır veya içinde **enum** kendisi (için kapsamlı numaralandırmalar). Adlara verilen değerlerin benzersiz olması gerekmez. Örneğin, kapsamsız bir enum bildirimi `Suit` budur:

```cpp
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };
```

Ardından değerlerini `Diamonds`, `Hearts`, `Clubs`, ve `Spades` 5, 6, 4 ve 5, sırasıyla. 5 kereden fazla kullanılmamasını dikkat edin. hazırlanmamış olsa bile bu izin verilir. Bu kurallar, kapsamı olan Enum'lar için aynıdır.

## <a name="casting-rules"></a>Dönüştürme kuralları

Kapsamı olmayan enum sabitleri örtük olarak dönüştürülebilir **int**, ancak bir **int** hiçbir zaman örtük olarak bir enum değerine dönüştürülebilir değildir. Aşağıdaki örnekte gösterildiği atamaya çalıştığınızda ne `hand` olmayan bir değer bir `Suit`:

```cpp
int account_num = 135692;
Suit hand;
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
```

Bir numaralandırmaya dönüştürmek için gerekli bir **int** için kapsamlı ya da kapsamsız bir numaralandırıcı. Ancak, kapsamsız bir numaralandırıcı bir yayın olmadan bir tamsayı değerine yükseltebilirsiniz.

```cpp
int account_num = Hearts; //OK if Hearts is in a unscoped enum
```

Örtük dönüştürmeleri bu şekilde kullanmak, istenmeyen yan etkilere neden neden olabilir. Kapsamı belirlenmemiş Enum'lar ile ilişkili programlama hatalarını gidermeye yardımcı olmak için kapsamı belirli enum değerleri kesin türlü yapılır. Kapsamlı numaralandırıcılar enum tür adı (tanımlayıcı) tarafından nitelendirilmelidir ve örtük olarak, aşağıdaki örnekte gösterildiği gibi dönüştürülemez:

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

Dikkat satır `hand = account_num;` hala daha önce gösterildiği gibi kapsamsız numaralandırmalar ile oluşan hataya neden. Bu, açık bir yayın ile izin verilir. Bununla birlikte, kapsamlı numaralandırmalar, denenen bir dönüştürme sonraki deyimi içinde `account_num = Suit::Hearts;`, artık açık bir yayın olmadan izin verilmez.

## <a name="no_enumerators"></a> Numaralandırmalar ile hiçbir numaralandırıcıları

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Açık bir temel alınan türü ile hiçbir numaralandırıcılar enum (normal veya kapsamlı) tanımlayarak, geçerli herhangi bir tür için örtük dönüştürme olan yeni bir integral türü ortaya çıkarabilir. Yerleşik temel alınan türü yerine bu türü kullanarak, ince hatalar nedeniyle yanlışlıkla örtük dönüştürmeler tarafından olasılığını ortadan kaldırabilir.

```cpp
enum class byte : unsigned char { };
```

Yeni türü temel tür tam bir kopyası ve bu nedenle herhangi bir performans cezası desteklenecek Abı'lerin kullanılabileceği anlamına gelir aynı çağrı kuralına sahiptir. Atama türü değişkenler doğrudan liste başlatma kullanılarak başlatılır gereklidir. Aşağıdaki örnek, sabit listeleri ile hiçbir numaralandırıcılar çeşitli bağlamlarda başlatmak gösterilmektedir:

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)