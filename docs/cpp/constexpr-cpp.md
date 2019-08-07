---
title: constexpr (C++)
ms.date: 08/05/2019
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
ms.openlocfilehash: 5c98436f537b34b1c9050e057971938d48792db1
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821104"
---
# <a name="constexpr-c"></a>constexpr (C++)

**Constexpr** anahtar sözcüğü, c++ 11 ' de tanıtılmıştı ve c++ 14 ' te geliştirildi. Bu, *sabit bir ifade*anlamına gelir. **Const**gibi, herhangi bir kod değeri değiştirmeye çalışırsa bir derleyici hatası ortaya çıktığında değişkenlere uygulanabilir. **Const**'in aksine, **constexpr** de işlevlere ve sınıf oluşturuculara uygulanabilir. **constexpr** değeri, değerin veya dönüş değerinin sabit olduğunu ve mümkünse derleme zamanında hesaplandığını gösterir.

Bir **constexpr** integral değeri, şablon bağımsız değişkenleri ve dizi bildirimleri gibi bir const tamsayı gerekli olduğunda kullanılabilir. Ayrıca, çalışma zamanı yerine derleme zamanında bir değer hesaplanabiliyor olması, programınızın daha hızlı çalışmasına ve daha az bellek kullanmasına yardımcı olabilir.

Derleme zamanı sabit hesaplamaların karmaşıklığını ve derleme süresi üzerinde olası etkileri sınırlamak için, C++ 14 standardı sabit deyimlerdeki türlerin [değişmez türler](trivial-standard-layout-and-pod-types.md#literal_types)olmasını gerektirir.

## <a name="syntax"></a>Sözdizimi

> **constexpr** *değişmez değer türü* *tanımlayıcı* **=** *sabit-ifade* **;** 
>  **constexpr** *değişmez değer türü* *tanımlayıcı* **{** *sabit-ifade* **}** **;** 
>  **constexpr** *değişmez değer türü* *tanımlayıcı* **(** *params* **)** **;** 
>  **constexpr** *ctor* **(** *params* **)** **;**

## <a name="parameters"></a>Parametreler

*params*<br/>
Her birinin sabit değer türü olması gereken bir veya daha fazla parametre, kendisi de sabit bir ifade olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Constexpr değişkeni veya işlevi bir [sabit değer türü](trivial-standard-layout-and-pod-types.md#literal_types)döndürmelidir.

## <a name="constexpr-variables"></a>constexpr değişkenleri

Const ve constexpr değişkenleri arasındaki birincil fark, bir const değişkeninin başlatılmasının çalışma zamanına kadar ertelenmesini sağlayabilir. Bir constexpr değişkeninin derleme zamanında başlatılması gerekir.  Tüm constexpr değişkenleri const.

- Bir değişken, bir sabit değer türüne sahipse ve başlatılmışsa, **constexpr**ile bildirilebilecek. Başlatma bir Oluşturucu tarafından gerçekleştirilirse, Oluşturucu **constexpr**olarak bildirilmelidir.

- Başvurduğu nesne sabit bir ifade tarafından başlatılmışsa ve başlatma sırasında çağrılan örtük dönüştürmeler de sabit ifadeler ise, başvuru constexpr olarak bildirilemez.

- **Constexpr** değişkeninin veya işlevinin tüm bildirimlerinin **constexpr** belirleyicisi olmalıdır.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a>constexpr işlevleri

Bir **constexpr** işlevi, dönüş değeri, kod tüketme gerektirdiğinde derleme zamanında hesaplanabilmesi gereken bir işlemdir. Kod tüketen, derleme zamanında dönüş değeri gerekir, örneğin, bir **constexpr** değişkeni başlatabilir veya tür olmayan bir şablon bağımsız değişkeni sağlayabilir. Bağımsız değişkenleri **constexpr** değerleri olduğunda, **constexpr** işlevi bir derleme zamanı sabiti üretir. **Constexpr** olmayan bağımsız değişkenlerle çağrıldığında veya derleme zamanında değeri gerekli olmadığında, bir normal işlev gibi çalışma zamanında bir değer üretir. (Bu çift davranış, aynı işlevin **constexpr** ve**constexpr** olmayan sürümlerini yazmak zorunda kalmanızı sağlar.)

**Constexpr** işlevi veya Oluşturucu örtük olarak **satır içi**olur.

Constexpr işlevleri için aşağıdaki kurallar geçerlidir:

- **Constexpr** işlevi yalnızca [sabit değer türlerini](trivial-standard-layout-and-pod-types.md#literal_types)kabul etmeli ve döndürmelidir.

- **Constexpr** işlevi yinelemeli olabilir.

- [Sanal](../cpp/virtual-cpp.md)olamaz. Kapsayan sınıfın herhangi bir sanal temel sınıfı varsa, bir Oluşturucu constexpr olarak tanımlanamaz.

- Gövde veya `= default` `= delete`olarak tanımlanabilir.

- Gövdede **goto** deyimi veya TRY blokları bulunabilir.

- Constexpr olmayan bir şablonun açık özelleştirmesi, **constexpr**olarak bildirilemez:

- **Constexpr** şablonunun açık özelleştirmesi aynı zamanda **constexpr**olmalıdır:

Aşağıdaki kurallar, Visual Studio 2017 ve üzeri bölümlerinde **constexpr** işlevleri için geçerlidir:

- **IF** ve **Switch** deyimlerini ve **için**, Aralık tabanlı for, **while**ve **do-while**gibi tüm döngü deyimlerini içerebilir.

- Yerel değişken bildirimleri içerebilir, ancak değişkenin başlatılmış olması, sabit bir tür olması ve statik veya iş parçacığı yerel olamaz. Yerel olarak belirtilen değişkenin const olması gerekmez ve Mutate olabilir.

- Constexpr statik olmayan bir üye işlevinin örtük olarak const olması gerekmez.

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio hata ayıklayıcıda, en iyi hale getirilmemiş bir hata ayıklama derlemesinde hata ayıklarken, içinde bir kesme noktası yerleştirerek bir **constexpr** işlevinin derleme zamanında değerlendirileceğini söyleyebilirsiniz. Kesme noktası isabet alıyorsa, işlev çalışma zamanında çağırılır.  Aksi takdirde, işlev derleme zamanında çağırılır.

## <a name="extern-constexpr"></a>extern constexpr

[/Zc: externConstexpr](../build/reference/zc-externconstexpr.md) derleyici seçeneği derleyicinin **extern constexpr**kullanılarak belirtilen değişkenlere [dış bağlantı](../c-language/external-linkage.md) uygulamasını sağlar. Visual Studio 'nun önceki sürümlerinde ve varsayılan olarak veya **/Zc: externConstexpr-** belirtilmişse, **extern** anahtar sözcüğü kullanılsa bile, Visual Studio **constexpr** değişkenlerine iç bağlantı uygular. **/Zc: externConstexpr** seçeneği, Visual Studio 2017 güncelleştirme 15,6 ' den başlayarak kullanılabilir ve varsayılan olarak kapalıdır. /Permissive-seçeneği **/Zc: externConstexpr**'yi etkinleştirmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **constexpr** değişkenlerini, işlevleri ve Kullanıcı tanımlı bir türü gösterir. Main () içindeki son ifadede, değer derleme zamanında bilinmesi gerekmediği için, bir çalışma zamanı çağrısı olan GetValue (), **constexpr** üye işlevi.

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
