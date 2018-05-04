---
title: constexpr (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- constexpr_cpp
dev_langs:
- C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f95f6c98138ff1eb52750c1b8593795ca28c784
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="constexpr-c"></a>constexpr (C++)

Anahtar sözcüğü **constexpr** C ++ 11'de tanıtılan ve C ++ 14'te geliştirildi. Geldiğini *sabit ifade*. Gibi **const**, böylece herhangi bir kod değeri değiştirmeye çalışırsa derleyici hatası gerçekleştirilecektir bu değişkenleri uygulanabilir. Farklı **const**, **constexpr** işlevler de uygulanabilir ve sınıf oluşturucularını. **constexpr** değer veya dönüş değeri, sabittir ve derleme zamanında hesaplanan Mümkünse, gösterir.

A **constexpr** tam sayı değeri const tamsayı, gibi bağımsız şablon ve dizi bildirimleri gerekli olduğunda kullanılabilir. Ve çalışma zamanında yerine derleme zamanında bir değer hesaplanan, daha hızlı çalışır ve daha az bellek kullanır, programınızı yardımcı olabilir.

Bilgi işlem derleme zamanı sabitleri karmaşıklığına ve bunların olası etkileri derleme süreyi sınırlamak için C ++ 14 standart sabit ifadeler ilgili türleri için sınırlı olmalıdır [değişmez değer türleri](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Sözdizimi

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>Parametreler

 *params*  
Değişmez değer türü olması gerekir ve kendisine gereken bir veya daha fazla parametre sabit bir ifade olması.

## <a name="return-value"></a>Dönüş Değeri


 Constexpr değişken veya işlev döndürmelidir bir [değişmez değer türü](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="constexpr-variables"></a>constexpr değişkenleri

 Const ve constexpr değişkenleri arasındaki birincil fark, bir constexpr değişken derleme zamanında başlatılmalıdır ise, başlatma const bir değişkenin çalışma zamanına kadar ertelenmiş ' dir.  Tüm constexpr const değişkenlerdir.

- Bir değişken ile bildirilen **constexpr**, değişmez değer türü varsa ve başlatılır. Başlatma oluşturucusu tarafından gerçekleştirilirse, oluşturucusu olarak bildirilmesi gerekir **constexpr**.

- Bir başvuru constexpr başvurduğu nesnenin sabit bir ifade tarafından başlatıldı ve başlatma sırasında çağrılan tüm örtük dönüşümler sabit ifadeler de bildirilebilir.

- Tüm bildirimlerini bir **constexpr** değişken veya işlev olmalıdır **constexpr** tanımlayıcısı.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> constexpr işlevleri

A **constexpr** işlevi bir dönüş değeri hesaplanan derleme kodu tüketen gerektirmesi durumunda olduğundan.  Bağımsız değişkenlerini olduğunda **constexpr** değerleri alabilir kod gerektirir ve dönüş değeri başlatmak örneğin derleme zamanında bir **constexpr** değişkeni ya da bir tür olmayan şablon bağımsız değişken sağlayın, derleme zamanı sabiti üretir. Olmayan ile çağrıldığında**constexpr** bağımsız değişken veya değerini derleme zamanında gerekli olmadığı durumlarda, bu değer normal bir işlev gibi çalışma zamanında üretir.  (Bu ikili davranış yazmak zorunda kalmaktan kaydeder **constexpr** ve olmayan-**constexpr** aynı işlevi sürümlerini.)

A **constexpr** işlevi Oluşturucusu mi örtük olarak **satır içi**.

Constexpr işlevleri için aşağıdaki kurallar geçerli olur:

- A **constexpr** işlevi kabul etmek ve yalnızca dönmek [değişmez değer türleri](trivial-standard-layout-and-pod-types.md#literal_types).

- A **constexpr** işlevi özyinelemeli olabilir.

- Olamaz [sanal](../cpp/virtual-cpp.md). A kapsayan sınıfın tüm sanal taban sınıflar varsa bir oluşturucu constexpr tanımlanamaz.

- Gövde olarak tanımlanabilir **= varsayılan** veya **= Sil**.

- Gövde Hayır içerebilir **goto** deyimleri veya try blokları.

- Bir açık alt uzmanlaşması constexpr olmayan şablon olarak bildirilebilir **constexpr**:

- Bir açık alt uzmanlaşması bir **constexpr** şablonu da gerekmez **constexpr**:

Aşağıdaki kurallar geçerli **constexpr** Visual Studio 2017 ve daha sonra işlevleri:

- İçeriyor olabilir **varsa** ve **geçiş** deyimleri ve de dahil olmak üzere tüm Döngü deyimleri **için**, aralık tabanlı, **sırada**ve **yapın-sırada**.
 
- Yerel değişken bildirimleri içerebilir, ancak değişkeni başlatılmalıdır, değişmez değer türü olmalıdır ve statik veya iş parçacığı yerel olamaz. Yerel olarak bildirilen değişken const olması gerekli değildir ve mutate.

- Constexpr statik olmayan üye işlevi örtük olarak const olması gerekli değildir.


```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Not: Visual Studio Hata Ayıklayıcısı'ndaki bir olmayan-en iyi duruma getirilmiş hata ayıklama hata ayıklarken yapı, size söyleyebilir olup bir **constexpr** işlevi değerlendirileceği derleme zamanında bir kesme noktası içindeki koyarak. Kesme noktası isabet durumunda işlevi çalışma zamanında çağrıldı.  Aksi durumda, işlevi derleme zamanında sonra çağrıldı.

## <a name="extern-constexpr"></a>extern constexpr

[/Zc:externConstexpr](../build/reference/zc-externconstexpr.md) derleyici seçeneği neden uygulamak derleyici [dış bağlantı]() kullanarak bildirilen değişkenlerin için **extern constexpr**. Visual Studio ve varsayılan olarak eski sürümlerinde veya **/Zc:externConstexpr-** belirtilirse, Visual Studio geçerlidir iç bağlantı **constexpr** olsa bile değişkenleri **extern** anahtar sözcüğü kullanılır. **/Zc:externConstexpr** Visual Studio 2017 güncelleştirme 15,6 başlangıç seçeneği kullanılabilir. ve varsayılan olarak kapalıdır. /Permissive-option /Zc:externConstexpr etkinleştirmez.

## <a name="example"></a>Örnek

 Aşağıdaki örnekte gösterildiği **constexpr** değişkenler, İşlevler ve kullanıcı tanımlı tür. Ana(), son deyimindeki unutmayın **constexpr** üye işlevi GetValue() olduğundan bir çalışma zamanı çağrı değeri derleme zamanında bilinmesi gerekli değildir.

```cpp
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

// Compile time computation of array length
template<typename T, int N>
constexpr int length(const T(&ary)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n*fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue()
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    //foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    //Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    //Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;

}

```

## <a name="requirements"></a>Gereksinimler

Visual Studio 2015

## <a name="see-also"></a>Ayrıca Bkz.

- [Bildirimler ve Tanımlar](../cpp/declarations-and-definitions-cpp.md)
- [const](../cpp/const-cpp.md)
