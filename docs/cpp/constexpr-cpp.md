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
ms.openlocfilehash: 150179fc0fd97450ba805d6957f5282bfaf8345c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071264"
---
# <a name="constexpr-c"></a>constexpr (C++)

Anahtar sözcüğü **constexpr** C ++ 11'de tanıtılan ve C ++ 14'te geliştirildi. Geldiğini *sabit ifade*. Gibi **const**, böylece herhangi bir kod değeri değiştirme girişiminde bulunursa, bir derleyici hatası gerçekleştirilecektir Bu değişkenlere uygulanabilir. Farklı **const**, **constexpr** işlevleri için de uygulanabilir ve sınıf oluşturucu. **constexpr** değeri ya da dönüş değeri sabittir ve mümkün olduğunda, derleme zamanında hesaplanacağı, gösterir.

A **constexpr** tamsayı değeri, const tamsayı, olduğu gibi şablon bağımsız değişkenleri ve dizi bildirimleri gereklidir her yerde kullanılabilir. Ve çalışma zamanı yerine derleme zamanında bir değer hesaplanır, programınızı daha hızlı çalışır ve daha az bellek kullanacak yardımcı olabilir.

Bilgi işlem derleme zamanı sabitleri karmaşıklığına ve derleme zamanı, olası etkilerini sınırlamak için C ++ 14 standart sabit ifadelerde ilgili türleri sınırlı olmasını gerektirir [değişmez değer türleri](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Sözdizimi

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>Parametreler

*params*<br/>
Değişmez değer türü olması gerekir ve kendisine gereken bir veya daha fazla parametre, sabit bir ifade olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Constexpr değişken veya işlev döndürmelidir bir [değişmez değer türü](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="constexpr-variables"></a>constexpr değişkenlerini

Const ve constexpr değişkenlerini arasındaki birincil fark, bir constexpr değişken derleme zamanında başlatılmalıdır ise, const bir değişkenin başlatılması çalışma zamanına kadar ertelenmiş ' dir.  Tüm constexpr değişkenlerini const.

- Bir değişken ile bildirilebilir **constexpr**, değişmez değer türü olan ve başlatılır. Başlatma Oluşturucu tarafından gerçekleştirilirse, oluşturucu olarak bildirilmesi gerekir **constexpr**.

- Bir başvuru, başvuran nesne sabit bir ifade tarafından başlatılmış ve başlatma sırasında çağrılan örtük dönüştürmeleri sabit ifadeler de constexpr bildirilebilir.

- Tüm bildirimleri bir **constexpr** değişken veya işlev olmalıdır **constexpr** tanımlayıcısı.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> constexpr işlevleri

A **constexpr** işlev, bir dönüş değeri hesaplanan derleme kodu kullanan gerektirmesi durumunda.  Bağımsız değişkenlerinden olduğunda **constexpr** değerleri kullanan kodu gerektirir ve dönüş değeri derleme zamanında, örneğin başlatmak bir **constexpr** değişkeni veya bir tür olmayan şablon bağımsız değişkeni sağlamak, bir derleme zamanı sabiti oluşturur. Non - çağrıldığında**constexpr** bağımsız değişkenleri, ya da değeri derleme zamanında gerekli değildir, bu değer bir normal işlev gibi çalışma zamanında üretir.  (Bu çift davranışı yazmak zorunda kalmaktan kurtarır **constexpr** ve olmayan-**constexpr** sürümleri aynı işlevin.)

A **constexpr** olan işlevde veya Oluşturucu örtük olarak **satır içi**.

Constexpr işlevleri için aşağıdaki kurallar geçerlidir:

- A **constexpr** işlevi kabul etmek ve yalnızca dönmek [değişmez değer türleri](trivial-standard-layout-and-pod-types.md#literal_types).

- A **constexpr** işlevi özyinelemeli olabilir.

- Olamaz [sanal](../cpp/virtual-cpp.md). Bir kapsayan sınıfa herhangi bir sanal temel sınıflar varsa, bir oluşturucu constexpr tanımlanamaz.

- Gövde olarak tanımlanabilir `= default` veya `= delete`.

- Gövde yok içerebilir **goto** deyimleri ya da try bloğu.

- Constexpr olmayan şablonun açık uzmanlığı olarak bildirilebilir **constexpr**:

- Bir açık alt uzmanlaşması bir **constexpr** şablon de gerekmez **constexpr**:

Aşağıdaki kurallar geçerli **constexpr** işlevleri Visual Studio 2017 ve sonraki sürümler:

- İçerebilir **varsa** ve **geçiş** deyimleri ve dahil tüm döngü deyimi **için**, aralığa dayalı for **sırada**ve **yapın-sırada**.

- Yerel değişken bildirimlerini içerebilir, ancak değişkenin başlatılması gerekir, değişmez değer türü olması gerekir ve statik veya iş parçacığı-yerel olamaz. Yerel olarak bildirilen değişken const olması gerekli değildir ve bulunmamalıdır.

- Constexpr statik olmayan üye işlev örtük olarak const olması gerekli değildir.

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Not: Visual Studio hata ayıklayıcısının bir olmayan-en iyi duruma getirilmiş hata ayıklamayı Debug, derleme, size söyleyebilir olup olmadığını bir **constexpr** işlevi değerlendirme derleme zamanında içine bir kesme noktası yerleştirerek. Kesme noktasına erişildiğinde, çalışma zamanında işlev çağrıldı.  Aksi durumda, işlev derleme zamanında ardından çağrıldı.

## <a name="extern-constexpr"></a>extern constexpr

[/ZC: externconstexpr](../build/reference/zc-externconstexpr.md) derleyici seçeneği, derleyicinin uygulamak neden [dış bağlantısı]() kullanılarak bildirilen değişkenlere **extern constexpr**. Varsayılan olarak ve Visual Studio'nun önceki sürümlerinde veya **/Zc:externConstexpr-** belirtilirse, Visual Studio iç bağlantı için geçerli **constexpr** değişkenleri bile **extern** anahtar sözcüğü kullanılır. **/ZC: externconstexpr** Visual Studio 2017 güncelleştirme 15.6 sürümünde başlangıç seçeneği kullanılabilir. ve varsayılan olarak kapalıdır. / ZC: externconstexpr /permissive-option etkinleştirmez.

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği **constexpr** değişkenler, İşlevler ve kullanıcı tanımlı bir tür. Ana(), işlemdeki son deyim içinde unutmayın **constexpr** üye işlevi GetValue() olduğundan çalışma zamanı arama değeri derleme zamanında bilinen gerekli değildir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Tanımlar](../cpp/declarations-and-definitions-cpp.md)<br/>
[const](../cpp/const-cpp.md)
