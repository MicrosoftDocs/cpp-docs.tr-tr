---
title: constexpr C++
description: C++ dili constexpr anahtar sözcüğüne kılavuz.
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
ms.openlocfilehash: 57ebf4bf69c768bfcd2e4d26a5c3334ca788b08f
ms.sourcegitcommit: a6b97f5d78299ad93675de2fe0f0561f528d26c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90569559"
---
# <a name="no-locconstexpr-c"></a>constexpr C++

Anahtar sözcüğü **`constexpr`** c++ 11 ' de tanıtılmıştır ve c++ 14 ' te geliştirilmiştir. Bu, * const ant ifadesi*anlamına gelir. Benzer şekilde **`const`** , değişkenler için de uygulanabilir: herhangi bir kod değeri bir değere ayarlamaya çalıştığında derleyici hatası tetiklenir if . Aksine **`const`** , **`constexpr`** işlevler ve sınıf ruörler için de uygulanabilir const . **`constexpr`** değerin veya dönüş değerinin, sahip olduğunu const ve ne zaman, derleme zamanında hesaplandığını gösterir.

**`constexpr`** Tam sayı değeri const , şablon bağımsız değişkenleri ve dizi bildirimleri gibi bir tamsayı gerekli olduğunda kullanılabilir. Çalışma zamanı yerine derleme sırasında bir değer hesaplanırsa, programınızın daha hızlı çalışmasına ve daha az bellek kullanmasına yardımcı olur.

Derleme zamanı const ant hesaplamaların karmaşıklığını ve derleme süresi üzerinde olası etkileri sınırlamak için, c++ 14 standardı, const ant ifadelerindeki türlerin [değişmez türler](trivial-standard-layout-and-pod-types.md#literal_types)olmasını gerektirir.

## <a name="syntax"></a>Syntax

> **`constexpr`***değişmez değer türü* * if * **=** * const ıkarant-Expression* **;**\
> **`constexpr`***sabit değerli tür* * if * kimliği \ **{** * const ant-Expression* **}** **;**\
> **`constexpr`***değişmez değer türü* * if * **(** *params* **)** **;**\
> **`constexpr`***ctor* **(** *params* **)** **;**

## <a name="parameters"></a>Parametreler

*parametrelerin*\
Her birinin bir sabit değer türü olması gereken ve kendisi bir ant ifadesi olması gereken bir veya daha fazla parametre const .

## <a name="return-value"></a>Döndürülen değer

**`constexpr`** Değişken veya işlev bir [sabit değer türü](trivial-standard-layout-and-pod-types.md#literal_types)döndürmelidir.

## <a name="no-locconstexpr-variables"></a>constexpr değişkenlerinin

ifVe değişkenleri arasındaki birincil d Ference, **`const`** **`constexpr`** bir **`const`** değişkenin başlatılmasının çalışma zamanına kadar ertelenebilir. Bir **`constexpr`** değişken derleme zamanında başlatılmalıdır.  Tüm **`constexpr`** değişkenler **`const`** .

- Bir değişken **`constexpr`** , bir sabit değer türüne sahip ve başlatıldığında ile bildirilemez. Başlatma for bir ructor tarafından med ise const , const ructor olarak bildirilmelidir **`constexpr`** .

- Bir başvuru, **`constexpr`** Bu koşulların her ikisi de karşılandığında olduğu gibi bildirilebilecek: başvurulan nesne bir const ant ifadesi tarafından başlatılır ve başlatma sırasında çağrılan örtük dönüştürmeler de const ant ifadeleridir.

- Bir **`constexpr`** değişken veya işlev için tüm bildirimlerin **`constexpr`** spec ier 'ı olmalıdır if .

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="no-locconstexpr-functions"></a><a name="constexpr_functions"></a>constexprişlevler

Bir **`constexpr`** işlev, kod tüketme gerektirdiğinde derleme zamanında dönüş değeri tablo olarak belirlenir. Kod tüketen, derleme zamanında bir **`constexpr`** değişken başlatmak veya tür olmayan bir şablon bağımsız değişkeni sağlamak için dönüş değeri gereklidir. Bağımsız değişkenleri değerler olduğunda **`constexpr`** , bir **`constexpr`** işlev derleme zamanı const ant üretir. **`constexpr`** Bağımsız değişkenlerle çağrıldığında veya derleme zamanında değeri gerekli olmadığında, çalışma zamanında normal bir işlev gibi bir değer oluşturur. (Bu çift davranış, **`constexpr`** aynı işlevin sürümlerini yazma ve sürüm olmayanlar için sizi kaydeder **`constexpr`** .)

**`constexpr`** İşlev veya const ructor örtük olarak **`inline`** .

İşlevler için aşağıdaki kurallar geçerlidir constexpr :

- Bir **`constexpr`** işlev yalnızca [sabit değer türlerini](trivial-standard-layout-and-pod-types.md#literal_types)kabul etmeli ve döndürmelidir.

- Bir **`constexpr`** işlev özyinelemeli olabilir.

- [Sanal](../cpp/virtual-cpp.md)olamaz. Bir const ructor **`constexpr`** , kapsayan sınıfın herhangi bir sanal temel sınıfa sahip olduğu zaman olarak tanımlanamaz.

- Gövde veya olarak tanımlanabilir `= default` `= delete` .

- Gövde hiçbir **`goto`** deyim veya **`try`** blok içerebilir.

- Şablon olmayan bir özelleşmenin açık bir özelleştirmesi **`constexpr`** şöyle bildirilebilecek **`constexpr`** :

- Bir şablonun açık özelleştirmesi **`constexpr`** de şunları yapmak zorunda değildir **`constexpr`** :

Aşağıdaki kurallar, **`constexpr`** Visual Studio 2017 ve üzeri işlevleri için geçerlidir:

- **`if`** **`switch`** , Ve deyimleri ve **`for`** , Aralık tabanlı **`for`** , **`while`** ** while **ve gibi tüm döngü deyimlerini içerebilir.

- Yerel değişken bildirimleri içerebilir, ancak değişkenin başlatılmış olması gerekir. Bu bir sabit değer türü olmalıdır ve **`static`** ya da iş parçacığı yerel olamaz. Yerel olarak belirtilen değişkenin olması gerekmez ve zaman zaman **`const`** olabilir.

- **`constexpr`** Üye olmayan bir **`static`** işlevin örtük olması gerekmez **`const`** .

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
}
```

> [!TIP]
> Visual Studio hata ayıklayıcıda, en iyi hale getirilmemiş bir hata ayıklama derlemesinde hata ayıklarken bir **`constexpr`** işlevin içine bir kesme noktası koyarak derleme zamanında değerlendirileceğini söyleyebilirsiniz. Kesme noktası isabet alıyorsa, işlev çalışma zamanında çağırılır.  Aksi takdirde, işlev derleme zamanında çağırılır.

## <a name="extern-no-locconstexpr"></a>Dış constexpr

[/Zc: externConstexpr](../build/reference/zc-externconstexpr.md) derleyici seçeneği derleyicinin [dış](../c-language/external-linkage.md) bağlantıyı **extern constexpr **kullanılarak belirtilen değişkenlere uygulamasını sağlar. Visual Studio 'nun önceki sürümlerinde, varsayılan olarak ya da **/Zc: externConstexpr-** spec olduğunda if , Visual Studio, **`constexpr`** anahtar sözcüğü kullanıldığında bile değişkenlere iç bağlantı uygular **`extern`** . **/Zc: externConstexpr** seçeneği, Visual Studio 2017 güncelleştirme 15,6 ' den başlayarak kullanılabilir ve varsayılan olarak kapalıdır. [/Permissive-](../build/reference/permissive-standards-conformance.md) seçeneği **/Zc: externConstexpr**'yi etkinleştirmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **`constexpr`** değişkenleri, işlevleri ve Kullanıcı tanımlı bir türü gösterir. İçindeki son ifadede `main()` , **`constexpr`** `GetValue()` değer derleme zamanında bilinmesi gerekmediği için üye işlevi bir çalışma zamanı çağrıdır.

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
}

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
}

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
