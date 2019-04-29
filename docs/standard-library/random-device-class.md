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
ms.openlocfilehash: 783b8f587094c6d603cc02f41b516ebd7b1e9a08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62369897"
---
# <a name="randomdevice-class"></a>random_device Sınıfı

Harici bir CİHAZDAN rastgele bir sıra üretir.

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
|[random_device](#random_device)|[entropi](#entropy)|
|[random_device::operator()](#op_call)||

## <a name="remarks"></a>Açıklamalar

Sınıfı rastgele sayıdan oluşan bir kaynak açıklar ve izin verilen ancak belirleyici olmayan veya şifreleme bakımından güvenli olacak şekilde ISO C++ standardı tarafından gerekli değildir. Visual Studio'da oluşturulan değerler belirleyici ve şifreleme yoluyla güvenli, uygulama ancak çalışan gelen altyapıları ve altyapısı bağdaştırıcıları oluşturulan oluşturucuları daha yavaş (gibi [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md), yüksek kaliteli ve uygulamalarının çoğu için tercih ettiğiniz hızlı altyapısı).

`random_device` sonuçları kapalı aralığında eşit dağıtılır [ `0, 2` <sup>32</sup>).

`random_device` Engelleyici olmayan bir çağrıda neden garanti edilmez.

Genellikle, `random_device` altyapıları veya altyapısı bağdaştırıcılar ile oluşturulan diğer oluşturucuları sağlamak için kullanılır. Daha fazla bilgi için [ \<rastgele >](../standard-library/random.md).

## <a name="example"></a>Örnek

Aşağıdaki kod, bu sınıf ve örnek sonuçları temel işlevselliğini gösterir. Belirleyici niteliği nedeniyle `random_device`, gösterilen rastgele değerler **çıkış** bölüm sonuçlarınızı eşleşmez. Normal ve beklenen budur.

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

Bu örnekte alıyormuş ve genel kullanım örneği bu oluşturucunun temsili. Daha fazla temsili bir kod örneği için bkz [ \<rastgele >](../standard-library/random.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="random_device"></a>  random_device::random_device

Oluşturucu oluşturur.

```cpp
random_device(const std::string& = "");
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, dize parametresi yok sayılıyor, gerektiği şekilde üreticiyi başlatır. Öğesinden türetilen uygulama tanımlı bir türde bir değer atar [özel durum](../standard-library/exception-class.md) varsa `random_device` başlatılamadı.

## <a name="entropy"></a>  random_device::Entropy

Kaynak rasgeleliğini tahmin eder.

```cpp
double entropy() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi bit cinsinden ölçülen kaynağın rastgeleliğinin bir tahminini döndürür.

## <a name="op_call"></a>  random_device::operator()

Rastgele bir değer döndürür.

```cpp
result_type operator()();
```

### <a name="remarks"></a>Açıklamalar

Kapalı aralık içerisinde birörnek dağıtılmış değerleri döndürür [ `min, max`] üye işlevleri tarafından belirlenen şekilde `min()` ve `max()`. Öğesinden türetilen uygulama tanımlı bir türde bir değer atar [özel durum](../standard-library/exception-class.md) , rastgele bir sayı sağlanamadı.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
