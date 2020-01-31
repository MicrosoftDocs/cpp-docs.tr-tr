---
title: constexpr (C++)
description: C++ Language constexpr anahtar sözcüğüne kılavuzluk edin.
ms.date: 01/28/2020
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- constexpr
- const
- inline
- goto
- try
- if
- switch
- for
- while
ms.openlocfilehash: 4f34eef3217377ab50a2d80d42b5bea4b054c5be
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821785"
---
# <a name="opno-locconstexpr-c"></a>constexpr (C++)

**constexpr** anahtar sözcüğü c++ 11 ' de tanıtılmıştır ve c++ 14 ' te geliştirilmiştir. Bu, *sabit bir ifade*anlamına gelir. **const** gibi, değişkenlere de uygulanabilir: herhangi bir kod değeri değiştirmeye çalıştığında bir derleyici hatası tetiklenir. **const** farklı olarak, **constexpr** işlevlere ve sınıf oluşturuculara da uygulanabilir. **constexpr** değerin veya dönüş değerinin sabit olduğunu ve mümkün olduğu durumlarda, derleme zamanında hesaplandığı anlamına gelir.

**constexpr** bir integral değeri, şablon bağımsız değişkenleri ve dizi bildirimleri gibi const bir tam sayının gerekli olduğu her yerde kullanılabilir. Çalışma zamanı yerine derleme sırasında bir değer hesaplanırsa, programınızın daha hızlı çalışmasına ve daha az bellek kullanmasına yardımcı olur.

Derleme zamanı sabit hesaplamaların karmaşıklığını ve derleme süresi üzerinde olası etkileri sınırlamak için, C++ 14 standardı sabit deyimlerdeki türlerin [değişmez türler](trivial-standard-layout-and-pod-types.md#literal_types)olmasını gerektirir.

## <a name="syntax"></a>Sözdizimi

> *sabit-ifade* **;** **constexpr** *değişmez değer türü* *tanımlayıcısı* **=** \
> **constexpr** *değişmez değer türü* *tanımlayıcı* **{** *sabit-ifade* **}** **;** \
> **constexpr** *değişmez değer türü* *tanımlayıcı* **(** *params* **)** **;** \
> **constexpr** *ctor* **(** *params* **)** **;**

## <a name="parameters"></a>Parametreler

*params*\
Her birinin sabit değer türü olması gereken bir veya daha fazla parametre, kendisi de sabit bir ifade olmalıdır.

## <a name="return-value"></a>Dönüş değeri

**constexpr** değişken veya işlev bir [sabit değer türü](trivial-standard-layout-and-pod-types.md#literal_types)döndürmelidir.

## <a name="opno-locconstexpr-variables"></a>constexpr değişkenleri

**const** ve **constexpr** değişkenleri arasındaki birincil fark, bir **const** değişkeninin başlatılmasının çalışma zamanına kadar ertelenebilir. Derleme zamanında bir **constexpr** değişkeni başlatılmalıdır.  Tüm **constexpr** değişkenleri **const** .

- Bir değişken, değişmez değer türüne sahip ve başlatıldığında **constexpr** ile bildirilemez. Başlatma bir Oluşturucu tarafından gerçekleştirilirse, Oluşturucu **constexpr** olarak bildirilmelidir.

- Bir başvuru, bu koşulların her ikisi de karşılandığında **constexpr** olarak bildirilebilecek: başvurulan nesne sabit bir ifade tarafından başlatılır ve başlatma sırasında çağrılan örtük dönüştürmeler de sabit ifadelerdir.

- Bir **constexpr** değişkenin veya işlevin tüm bildirimlerinin **constexpr** tanımlayıcısı olmalıdır.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a>constexpr işlevleri

Bir **constexpr** işlevi, dönüş değeri, kod tüketen derleme sırasında tablo oluşturma sırasında oluşturulabilir. Kod kullanan bir **constexpr** değişkeni başlatmak veya tür olmayan bir şablon bağımsız değişkeni sağlamak için derleme zamanında dönüş değeri gereklidir. Bağımsız değişkenleri **constexpr** değerler olduğunda, bir **constexpr** işlevi bir derleme zamanı sabiti üretir. **constexpr** olmayan bağımsız değişkenlerle çağrıldığında veya derleme zamanında değeri gerekli olmadığında, bir normal işlev gibi çalışma zamanında bir değer üretir. (Bu çift davranış aynı işlevin **constexpr** ve **constexpr** olmayan sürümlerini yazmak zorunda kalmanızı sağlar.)

**constexpr** işlev veya Oluşturucu örtük olarak **inline** .

constexpr işlevler için aşağıdaki kurallar geçerlidir:

- **constexpr** işlev yalnızca [sabit değer türlerini](trivial-standard-layout-and-pod-types.md#literal_types)kabul etmeli ve döndürmelidir.

- Bir **constexpr** işlevi yinelemeli olabilir.

- [Sanal](../cpp/virtual-cpp.md)olamaz. Kapsayıcı sınıfın herhangi bir sanal temel sınıfı olduğunda **constexpr** bir Oluşturucu tanımlanamaz.

- Gövde `= default` veya `= delete`olarak tanımlanabilir.

- Gövdede **goto** deyimi veya **try** blokları bulunabilir.

- **constexpr** olmayan bir şablonun açık özelleştirmesi, **constexpr** olarak bildirilemez:

- **constexpr** şablonun açık bir özelleştirmesi de **constexpr** olmak zorunda değildir:

Aşağıdaki kurallar, Visual Studio 2017 ve üzeri sürümlerde **constexpr** işlevleri için geçerlidir:

- **if** ve **switch** deyimlerini ve **for** , Aralık tabanlı **for** , **while** ve **Do-while** dahil tüm döngü deyimlerini içerebilir.

- Yerel değişken bildirimleri içerebilir, ancak değişkenin başlatılmış olması gerekir. Bu bir sabit değer türü olmalıdır ve **statik** veya iş parçacığı yerel olamaz. Yerel olarak belirtilen değişkenin **const** olması gerekmez ve zaman zaman olabilir.

- **constexpr** **statik** olmayan bir üye işlevinin örtük olarak **const** olması gerekmez.

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio hata ayıklayıcıda, en iyi hale getirilmemiş bir hata ayıklama derlemesinde hata ayıklarken, içine bir kesme noktası yerleştirerek **constexpr** işlevinin derleme zamanında değerlendirileceğini anlayabilirsiniz. Kesme noktası isabet alıyorsa, işlev çalışma zamanında çağırılır.  Aksi takdirde, işlev derleme zamanında çağırılır.

## <a name="extern-opno-locconstexpr"></a>extern constexpr

[/Zc: externConstexpr](../build/reference/zc-externconstexpr.md) derleyici seçeneği derleyicinin **extern constexpr** kullanılarak belirtilen değişkenlere [dış bağlantı](../c-language/external-linkage.md) uygulamasını sağlar. Visual Studio 'nun önceki sürümlerinde, varsayılan olarak veya **/Zc: externConstexpr-** belirtildiğinde, **extern** anahtar sözcüğü kullanıldığında bile Visual Studio **constexpr** değişkenlerine iç bağlantı uygular. **/Zc: externConstexpr** seçeneği, Visual Studio 2017 güncelleştirme 15,6 ' den başlayarak kullanılabilir ve varsayılan olarak kapalıdır. [/Permissive-](../build/reference/permissive-standards-conformance.md) seçeneği **/Zc: externConstexpr**'yi etkinleştirmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **constexpr** değişkenleri, işlevleri ve Kullanıcı tanımlı bir türü gösterir. `main()`' deki son ifadede, değerin derleme zamanında bilinmesi gerekmediği için, **constexpr** üye işlevi `GetValue()` bir çalışma zamanı çağrıdır.

```cpp
// constexpr.cpp
// Compile with: cl /EHsc /W4 constexpr.cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile-time computation of array length
template<typename T, int N>
constexpr int length(const T(&)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue() const
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>Gereksinimler

Visual Studio 2015 veya üzeri.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve tanımlar](../cpp/declarations-and-definitions-cpp.md)\
[const](../cpp/const-cpp.md)
