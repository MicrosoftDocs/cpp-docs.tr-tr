---
title: random_device Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::random_device
- random/std::random_device::min
- random/std::random_device::max
- random/std::random_device::entropy
- random/std::random_device::operator()
helpviewer_keywords:
- std::random_device [C++]
- std::random_device [C++], min
- std::random_device [C++], max
- std::random_device [C++], entropy
- std::random_device [C++], entropy
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
ms.openlocfilehash: 396f172d6a7f9fed72e19917a528f561d0110470
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320267"
---
# <a name="random_device-class"></a>random_device Sınıfı

Harici bir aygıttan rasgele bir sıra oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
class random_device {
public:
   typedef unsigned int result_type;

   // constructor
   explicit random_device(const std::string& token = "");

   // properties
   static result_type min();
   static result_type max();
   double entropy() const;

   // generate
   result_type operator()();

   // no-copy functions
   random_device(const random_device&) = delete;
   void operator=(const random_device&) = delete;
   };
```

## <a name="members"></a>Üyeler

|||
|-|-|
|[random_device](#random_device)|[entropy](#entropy)|
|[random_device::operator()](#op_call)||

## <a name="remarks"></a>Açıklamalar

Sınıf rasgele sayılar kaynağını açıklar ve ISO C++ Standardı tarafından deterministik olmayan veya şifreleme açısından güvenli olması gerekmez. Visual Studio uygulamasında üretilen değerler deterministik olmayan ve şifreleme açısından güvenlidir, ancak motorve motor adaptörlerinden oluşturulan jeneratörlerden [(mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)gibi, çoğu uygulama için tercih edilen yüksek kaliteli ve hızlı motor) daha yavaş çalışır.

`random_device`sonuçlar kapalı aralıkta eşit olarak `0, 2`dağıtılır [ <sup>32</sup>).

`random_device`engelleyici olmayan bir çağrıyla sonuçlanması garanti edilmez.

Genellikle, `random_device` motor veya motor adaptörleri ile oluşturulan diğer jeneratörler tohum için kullanılır. Daha fazla bilgi için [ \<rastgele>](../standard-library/random.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki kod, bu sınıfın temel işlevselliğini ve örnek sonuçlarını gösterir. Deterministik olmayan yapısı `random_device`nedeniyle, **Çıktı** bölümünde gösterilen rasgele değerler sonuçlarınızla eşleşmez. Bu normal ve beklenen.

```cpp
// random_device_engine.cpp
// cl.exe /W4 /nologo /EHsc /MTd
#include <random>
#include <iostream>
using namespace std;

int main()
{
    random_device gen;

    cout << "entropy == " << gen.entropy() << endl;
    cout << "min == " << gen.min() << endl;
    cout << "max == " << gen.max() << endl;

    cout << "a random value == " << gen() << endl;
    cout << "a random value == " << gen() << endl;
    cout << "a random value == " << gen() << endl;
}
```

```Output
entropy == 32
min == 0
max == 4294967295
a random value == 2378414971
a random value == 3633694716
a random value == 213725214
```

Bu örnek basit ve bu jeneratör için genel kullanım örneği temsilcisi değildir. Daha temsili bir kod örneği için [ \<rasgele>](../standard-library/random.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<rastgele>

**Ad alanı:** std

## <a name="random_devicerandom_device"></a><a name="random_device"></a>random_device:random_device

Jeneratörü inşa eder.

```cpp
random_device(const std::string& = "");
```

### <a name="remarks"></a>Açıklamalar

Yapıcı, dize parametresini yoksayarak jeneratörü gerektiği gibi devreye alır. Başharflere `random_device` alınamadıysa, [özel durum](../standard-library/exception-class.md) türetilen uygulama tanımlı bir türün değerini atar.

## <a name="random_deviceentropy"></a><a name="entropy"></a>random_device::entropi

Kaynağın rastgeleliğini tahmin ediyor.

```cpp
double entropy() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, bit cinsinden ölçüldüğü gibi kaynağın rastgeleliğinin bir tahminini döndürür.

## <a name="random_deviceoperator"></a><a name="op_call"></a>random_device::operator()

Rasgele bir değer verir.

```cpp
result_type operator()();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevler `min, max` `min()` tarafından belirlenen kapalı aralıkta eşit olarak `max()`dağıtılan değerleri [ ] döndürür ve . Rasgele bir sayı elde edilemediyse, [özel durum](../standard-library/exception-class.md) türetilen uygulama tanımlı bir türün değerini atar.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele>](../standard-library/random.md)
