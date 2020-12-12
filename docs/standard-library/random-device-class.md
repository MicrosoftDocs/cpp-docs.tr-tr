---
description: 'Hakkında daha fazla bilgi edinin: random_device sınıfı'
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
ms.openlocfilehash: 29f7f9d1359e488bbe15811193c034a0be12219b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207481"
---
# <a name="random_device-class"></a>random_device Sınıfı

Dış cihazdan rastgele bir sıra üretir.

## <a name="syntax"></a>Syntax

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

[random_device](#random_device)\
[iyi](#entropy)\
[random_device:: operator ()](#op_call)

## <a name="remarks"></a>Açıklamalar

Sınıfı rastgele sayıların kaynağını açıklar ve izin verilir, ancak ISO C++ standardı tarafından belirleyici olmayan veya şifreli olarak güvenli olması gerekmez. Visual Studio uygulamasında oluşturulan değerler belirleyici değildir ve şifreli olarak güvende değildir, ancak altyapılardan ve altyapı bağdaştırıcılarında oluşturulan ( [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md), çoğu uygulama için tercih edilen yüksek kaliteli ve hızlı altyapıdan çok daha yavaş çalışır).

`random_device`sonuçlar kapalı [32) aralığında eşit olarak dağıtılır `0, 2` <sup></sup>.

`random_device` engellenmeyen bir çağrıya neden olması garanti edilmez.

Genellikle `random_device` altyapılarla veya altyapı bağdaştırıcılarında oluşturulan diğer yapıları temel almak için kullanılır. Daha fazla bilgi için bkz. [\<random>](../standard-library/random.md).

## <a name="example"></a>Örnek

Aşağıdaki kod, bu sınıfın temel işlevlerini ve örnek sonuçları gösterir. Belirleyici olmayan doğası nedeniyle `random_device` , **Çıkış** bölümünde gösterilen rastgele değerler sonuçlarınıza uymuyor. Bu normaldir ve beklenmektedir.

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

Bu örnek, uyarlaması ' dir ve bu oluşturucunun genel kullanım örneği temsilcisidir. Daha fazla temsili bir kod örneği için bkz [\<random>](../standard-library/random.md) ..

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="random_devicerandom_device"></a><a name="random_device"></a> random_device:: random_device

Oluşturucuyu oluşturur.

```cpp
random_device(const std::string& = "");
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, oluşturucuyu gereken şekilde başlatır, dize parametresini yoksayar. Başlatılamadı durumunda [özel](../standard-library/exception-class.md) durumdan türetilmiş uygulama tanımlı türün değerini oluşturur `random_device` .

## <a name="random_deviceentropy"></a><a name="entropy"></a> random_device:: entropi

Kaynağın rasgeleliğini tahmin eder.

```cpp
double entropy() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bit cinsinden ölçülen kaynağın rasgeleliğini tahmin eden bir değer döndürür.

## <a name="random_deviceoperator"></a><a name="op_call"></a> random_device:: operator ()

Rastgele bir değer döndürür.

```cpp
result_type operator()();
```

### <a name="remarks"></a>Açıklamalar

`min, max`Üye işlevleri ve tarafından belirlendiği şekilde kapalı [] aralığında dağıtılmış değerleri döndürür `min()` `max()` . Rastgele bir sayı alınamadığından [özel durumdan](../standard-library/exception-class.md) türetilen uygulama tanımlı türün değerini oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
