---
title: :::no-loc(constexpr):::C++
description: 'C++ dili :::no-loc(constexpr)::: anahtar sözcüğüne kılavuz.'
ms.date: 01/28/2020
f1_keywords:
- :::no-loc(constexpr):::_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- ':::no-loc(constexpr):::'
- ':::no-loc(const):::'
- ':::no-loc(inline):::'
- ':::no-loc(goto):::'
- ':::no-loc(try):::'
- ':::no-loc(if):::'
- ':::no-loc(switch):::'
- ':::no-loc(for):::'
- ':::no-loc(while):::'
ms.openlocfilehash: d66dc333b7ac9fba94221dc4efa723c7919ef88f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229031"
---
# <a name="no-locconstexpr-c"></a>:::no-loc(constexpr):::C++

Anahtar sözcüğü **`:::no-loc(constexpr):::`** c++ 11 ' de tanıtılmıştır ve c++ 14 ' te geliştirilmiştir. Bu, * :::no-loc(const)::: ant ifadesi*anlamına gelir. Benzer şekilde **`:::no-loc(const):::`** , değişkenler için de uygulanabilir: herhangi bir kod değeri bir değere ayarlamaya çalıştığında derleyici hatası tetiklenir :::no-loc(if)::: . Aksine **`:::no-loc(const):::`** , **`:::no-loc(constexpr):::`** işlevler ve sınıf ruörler için de uygulanabilir :::no-loc(const)::: . **`:::no-loc(constexpr):::`** değerin veya dönüş değerinin, sahip olduğunu :::no-loc(const)::: ve ne zaman, derleme zamanında hesaplandığını gösterir.

**`:::no-loc(constexpr):::`** Tam sayı değeri :::no-loc(const)::: , şablon bağımsız değişkenleri ve dizi bildirimleri gibi bir tamsayı gerekli olduğunda kullanılabilir. Çalışma zamanı yerine derleme sırasında bir değer hesaplanırsa, programınızın daha hızlı çalışmasına ve daha az bellek kullanmasına yardımcı olur.

Derleme zamanı :::no-loc(const)::: ant hesaplamaların karmaşıklığını ve derleme süresi üzerinde olası etkileri sınırlamak için, c++ 14 standardı, :::no-loc(const)::: ant ifadelerindeki türlerin [değişmez türler](trivial-standard-layout-and-pod-types.md#literal_types)olmasını gerektirir.

## <a name="syntax"></a>Sözdizimi

> **`:::no-loc(constexpr):::`***değişmez değer türü* * :::no-loc(if)::: * **=** * :::no-loc(const)::: ıkarant-Expression* **;**\
> **`:::no-loc(constexpr):::`***sabit değerli tür* * :::no-loc(if)::: * kimliği \ **{** * :::no-loc(const)::: ant-Expression* **}** **;**\
> **`:::no-loc(constexpr):::`***değişmez değer türü* * :::no-loc(if)::: * **(** *params* **)** **;**\
> **`:::no-loc(constexpr):::`***ctor* **(** *params* **)** **;**

## <a name="parameters"></a>Parametreler

*parametrelerin*\
Her birinin bir sabit değer türü olması gereken ve kendisi bir ant ifadesi olması gereken bir veya daha fazla parametre :::no-loc(const)::: .

## <a name="return-value"></a>Döndürülen değer

**`:::no-loc(constexpr):::`** Değişken veya işlev bir [sabit değer türü](trivial-standard-layout-and-pod-types.md#literal_types)döndürmelidir.

## <a name="no-locconstexpr-variables"></a>:::no-loc(constexpr):::değişkenlerinin

:::no-loc(if):::Ve değişkenleri arasındaki birincil d Ference, **`:::no-loc(const):::`** **`:::no-loc(constexpr):::`** bir **`:::no-loc(const):::`** değişkenin başlatılmasının çalışma zamanına kadar ertelenebilir. Bir **`:::no-loc(constexpr):::`** değişken derleme zamanında başlatılmalıdır.  Tüm **`:::no-loc(constexpr):::`** değişkenler **`:::no-loc(const):::`** .

- Bir değişken **`:::no-loc(constexpr):::`** , bir sabit değer türüne sahip ve başlatıldığında ile bildirilemez. Başlatma :::no-loc(for)::: bir ructor tarafından med ise :::no-loc(const)::: , :::no-loc(const)::: ructor olarak bildirilmelidir **`:::no-loc(constexpr):::`** .

- Bir başvuru, **`:::no-loc(constexpr):::`** Bu koşulların her ikisi de karşılandığında olduğu gibi bildirilebilecek: başvurulan nesne bir :::no-loc(const)::: ant ifadesi tarafından başlatılır ve başlatma sırasında çağrılan örtük dönüştürmeler de :::no-loc(const)::: ant ifadeleridir.

- Bir **`:::no-loc(constexpr):::`** değişken veya işlev için tüm bildirimlerin **`:::no-loc(constexpr):::`** spec ier 'ı olmalıdır :::no-loc(if)::: .

```cpp
:::no-loc(constexpr)::: float x = 42.0;
:::no-loc(constexpr)::: float y{108};
:::no-loc(constexpr)::: float z = exp(5, 3);
:::no-loc(constexpr)::: int i; // Error! Not initialized
int j = 0;
:::no-loc(constexpr)::: int k = j + 1; //Error! j not a :::no-loc(const):::ant expression
```

## <a name="no-locconstexpr-functions"></a><a name=":::no-loc(constexpr):::_functions"></a>:::no-loc(constexpr):::işlevler

Bir **`:::no-loc(constexpr):::`** işlev, kod tüketme gerektirdiğinde derleme zamanında dönüş değeri tablo olarak belirlenir. Kod tüketen, derleme zamanında bir **`:::no-loc(constexpr):::`** değişken başlatmak veya tür olmayan bir şablon bağımsız değişkeni sağlamak için dönüş değeri gereklidir. Bağımsız değişkenleri değerler olduğunda **`:::no-loc(constexpr):::`** , bir **`:::no-loc(constexpr):::`** işlev derleme zamanı :::no-loc(const)::: ant üretir. **`:::no-loc(constexpr):::`** Bağımsız değişkenlerle çağrıldığında veya derleme zamanında değeri gerekli olmadığında, çalışma zamanında normal bir işlev gibi bir değer oluşturur. (Bu çift davranış, **`:::no-loc(constexpr):::`** aynı işlevin sürümlerini yazma ve sürüm olmayanlar için sizi kaydeder **`:::no-loc(constexpr):::`** .)

**`:::no-loc(constexpr):::`** İşlev veya :::no-loc(const)::: ructor örtük olarak **`:::no-loc(inline):::`** .

İşlevler için aşağıdaki kurallar geçerlidir :::no-loc(constexpr)::: :

- Bir **`:::no-loc(constexpr):::`** işlev yalnızca [sabit değer türlerini](trivial-standard-layout-and-pod-types.md#literal_types)kabul etmeli ve döndürmelidir.

- Bir **`:::no-loc(constexpr):::`** işlev özyinelemeli olabilir.

- [Sanal](../cpp/virtual-cpp.md)olamaz. Bir :::no-loc(const)::: ructor **`:::no-loc(constexpr):::`** , kapsayan sınıfın herhangi bir sanal temel sınıfa sahip olduğu zaman olarak tanımlanamaz.

- Gövde veya olarak tanımlanabilir `= default` `= delete` .

- Gövde hiçbir **`:::no-loc(goto):::`** deyim veya **`:::no-loc(try):::`** blok içerebilir.

- Şablon olmayan bir özelleşmenin açık bir özelleştirmesi **`:::no-loc(constexpr):::`** şöyle bildirilebilecek **`:::no-loc(constexpr):::`** :

- Bir şablonun açık özelleştirmesi **`:::no-loc(constexpr):::`** de şunları yapmak zorunda değildir **`:::no-loc(constexpr):::`** :

Aşağıdaki kurallar, **`:::no-loc(constexpr):::`** Visual Studio 2017 ve üzeri işlevleri için geçerlidir:

- **`:::no-loc(if):::`** **`:::no-loc(switch):::`** , Ve deyimleri ve **`:::no-loc(for):::`** , Aralık tabanlı **`:::no-loc(for):::`** , **`:::no-loc(while):::`** ** :::no-loc(while)::: **ve gibi tüm döngü deyimlerini içerebilir.

- Yerel değişken bildirimleri içerebilir, ancak değişkenin başlatılmış olması gerekir. Bu bir sabit değer türü olmalıdır ve **`static`** ya da iş parçacığı yerel olamaz. Yerel olarak belirtilen değişkenin olması gerekmez ve zaman zaman **`:::no-loc(const):::`** olabilir.

- **`:::no-loc(constexpr):::`** Üye olmayan bir **`static`** işlevin örtük olması gerekmez **`:::no-loc(const):::`** .

```cpp
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio hata ayıklayıcıda, en iyi hale getirilmemiş bir hata ayıklama derlemesinde hata ayıklarken bir **`:::no-loc(constexpr):::`** işlevin içine bir kesme noktası koyarak derleme zamanında değerlendirileceğini söyleyebilirsiniz. Kesme noktası isabet alıyorsa, işlev çalışma zamanında çağırılır.  Aksi takdirde, işlev derleme zamanında çağırılır.

## <a name="extern-no-locconstexpr"></a>Dış:::no-loc(constexpr):::

[/Zc: externConstexpr](../build/reference/zc-extern:::no-loc(constexpr):::.md) derleyici seçeneği derleyicinin [dış](../c-language/external-linkage.md) bağlantıyı **extern :::no-loc(constexpr)::: **kullanılarak belirtilen değişkenlere uygulamasını sağlar. Visual Studio 'nun önceki sürümlerinde, varsayılan olarak ya da **/Zc: externConstexpr-** spec olduğunda :::no-loc(if)::: , Visual Studio, **`:::no-loc(constexpr):::`** anahtar sözcüğü kullanıldığında bile değişkenlere iç bağlantı uygular **`extern`** . **/Zc: externConstexpr** seçeneği, Visual Studio 2017 güncelleştirme 15,6 ' den başlayarak kullanılabilir ve varsayılan olarak kapalıdır. [/Permissive-](../build/reference/permissive-standards-con:::no-loc(for):::mance.md) seçeneği **/Zc: externConstexpr**'yi etkinleştirmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **`:::no-loc(constexpr):::`** değişkenleri, işlevleri ve Kullanıcı tanımlı bir türü gösterir. İçindeki son ifadede `main()` , **`:::no-loc(constexpr):::`** `GetValue()` değer derleme zamanında bilinmesi gerekmediği için üye işlevi bir çalışma zamanı çağrıdır.

```cpp
// :::no-loc(constexpr):::.cpp
// Compile with: cl /EHsc /W4 :::no-loc(constexpr):::.cpp
#include <iostream>

using namespace std;

// Pass by value
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
:::no-loc(constexpr)::: float exp2(:::no-loc(const)::: float& x, :::no-loc(const)::: int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile-time computation of array length
template<typename T, int N>
:::no-loc(constexpr)::: int length(:::no-loc(const)::: T(&)[N])
{
    return N;
}

// Recursive :::no-loc(constexpr)::: function
:::no-loc(constexpr)::: int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    :::no-loc(constexpr)::: explicit Foo(int i) : _i(i) {}
    :::no-loc(constexpr)::: int GetValue() :::no-loc(const):::
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is :::no-loc(const)::::
    :::no-loc(constexpr)::: Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    :::no-loc(constexpr)::: float x = exp(5, 3);
    :::no-loc(constexpr)::: float y { exp(2, 5) };
    :::no-loc(constexpr)::: int val = foo.GetValue();
    :::no-loc(constexpr)::: int f5 = fac(5);
    :::no-loc(const)::: int nums[] { 1, 2, 3, 4 };
    :::no-loc(const)::: int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>Gereksinimler

Visual Studio 2015 veya üzeri.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve tanımlar](../cpp/declarations-and-definitions-cpp.md)\
[:::no-loc(const):::](../cpp/:::no-loc(const):::-cpp.md)
