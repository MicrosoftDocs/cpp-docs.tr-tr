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
ms.openlocfilehash: 184513bc63975bd8eaaf0e53300e5a6be7986389
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448530"
---
# <a name="randomdevice-class"></a>random_device Sınıfı

Dış cihazdan rastgele bir sıra üretir.

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
|[random_device](#random_device)|[iyi](#entropy)|
|[random_device::operator()](#op_call)||

## <a name="remarks"></a>Açıklamalar

Sınıfı rastgele sayıların kaynağını açıklar ve izin verilir, ancak ISO C++ standardı tarafından belirleyici olmayan veya şifreli olarak güvenli olması gerekmez. Visual Studio uygulamasında oluşturulan değerler belirleyici değildir ve şifreli olarak güvenlidir, ancak altyapılardan ve altyapı bağdaştırıcılarında ( [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)gibi yüksek kaliteli ve hızlı) oluşturulan oluşturandan daha yavaş çalışır. Çoğu uygulama için tercih edilen altyapı.

`random_device`sonuçlar kapalı [ `0, 2` <sup>32</sup>) aralığında eşit olarak dağıtılır.

`random_device`engellenmeyen bir çağrıya neden olması garanti edilmez.

`random_device` Genellikle altyapılarla veya altyapı bağdaştırıcılarında oluşturulan diğer yapıları temel almak için kullanılır. Daha fazla bilgi için bkz [ \<. Random >](../standard-library/random.md).

## <a name="example"></a>Örnek

Aşağıdaki kod, bu sınıfın temel işlevlerini ve örnek sonuçları gösterir. Belirleyici olmayan doğası `random_device`nedeniyle, **Çıkış** bölümünde gösterilen rastgele değerler sonuçlarınıza uymuyor. Bu normaldir ve beklenmektedir.

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

Bu örnek, uyarlaması ' dir ve bu oluşturucunun genel kullanım örneği temsilcisidir. Daha fazla temsili bir kod örneği için bkz [ \<. Random >](../standard-library/random.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<rastgele >

**Ad alanı:** std

## <a name="random_device"></a>random_device::random_device

Oluşturucuyu oluşturur.

```cpp
random_device(const std::string& = "");
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, oluşturucuyu gereken şekilde başlatır, dize parametresini yoksayar. Başlatılamadı durumunda `random_device` [özel](../standard-library/exception-class.md) durumdan türetilmiş uygulama tanımlı türün değerini oluşturur.

## <a name="entropy"></a>random_device:: entropi

Kaynağın rasgeleliğini tahmin eder.

```cpp
double entropy() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bit cinsinden ölçülen kaynağın rasgeleliğini tahmin eden bir değer döndürür.

## <a name="op_call"></a>random_device:: operator ()

Rastgele bir değer döndürür.

```cpp
result_type operator()();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevleri `min, max` `min()` ve tarafındanbelirlendiğişekildekapalı[]aralığındadağıtılmışdeğerleridöndürür.`max()` Rastgele bir sayı alınamadığından [özel durumdan](../standard-library/exception-class.md) türetilen uygulama tanımlı türün değerini oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[\<Rastgele >](../standard-library/random.md)
