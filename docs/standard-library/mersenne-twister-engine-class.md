---
title: mersenne_twister_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::mersenne_twister_engine
helpviewer_keywords:
- mersenne_twister_engine class
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
ms.openlocfilehash: c0f30eacb308da61064a0383a6433b7127032a3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607460"
---
# <a name="mersennetwisterengine-class"></a>mersenne_twister_engine Sınıfı

Mersenne bükücü algoritmasına göre tamsayı yüksek kaliteli rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class UIntType,
    size_t W, size_t N, size_t M, size_t R,
    UIntType A, size_t U, UIntType D, size_t S,
    UIntType B, size_t T, UIntType C, size_t L, UIntType F>
class mersenne_twister_engine;
```

### <a name="parameters"></a>Parametreler

*UIntType*<br/>
İşeritsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*W*<br/>
**Word boyutu**. Her sözcüğün bitlerini durum sırası boyutu. **Önkoşul**: `2u < W ≤ numeric_limits<UIntType>::digits`

*N*<br/>
**Durum boyutu**. (Değerler) durumu dizideki öğelerin sayısı.

*M*<br/>
**Kaydırma boyutu**. Her geçiş sırasında atlanacak öğe sayısı. **Önkoşul**: `0 < M ≤ N`

*R*<br/>
**Bit maskesi**. **Önkoşul**: `R ≤ W`

*A*<br/>
**XOR maskesi**. **Önkoşul**: `A ≤ (1u<<W) - 1u`

*U*, *S*, *T*, *M*<br/>
**Shift parametreleri tempering**. Shift değerleri olarak (tempering) karıştırma sırasında kullanılır. Önkoşul: `U,S,T,L ≤ W`

*D*, *B*, *C*<br/>
**Bit maskesi parametreleri tempering**. Bit maskesi değerleri (tempering) karıştırma sırasında kullanılır. Önkoşul: `D,B,C ≤ (1u<<W) - 1u`

*F*<br/>
**Başlatma çarpan**. Başlatma sırası ile yardımcı olmak için kullanılır. Önkoşul: `F ≤ (1u<<W) - 1u`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|

`default_seed` üye sabit, olarak tanımlı `5489u`için varsayılan parametre değeri olarak kullanılır `mersenne_twister_engine::seed` ve tek değer Oluşturucusu.

Altyapısı üyeleri hakkında daha fazla bilgi için bkz. [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfı kapalı aralıkta değerler döndüren bir rastgele sayı altyapısı tanımlar [ `0`, `2` <sup>W</sup> - `1`]. Büyük bir dahili değer saklar `W * (N - 1) + R` bitleri. Ayıklar *W* bitleri teker teker bu büyük bir değer ve tüm bitleri kullandığında kaydırarak ve ayıklamak için BITS yeni bir dizi sahip olacak şekilde karıştırarak büyük bir değer büker bu. Son altyapının durumunda `N` `W`-bit değerleri kullanılıyorsa `operator()` en az adlı *N* zaman, aksi takdirde `M` `W`-bit kullanılmış olan değerleri ve son `N - M` çekirdek değerleri.

Oluşturucu shift değerler tarafından tanımlanan bir bükümlü genelleştirilmiş geri bildirim shift kayıt kullanarak tutan büyük değeri büker *N* ve *M*, bir sürpriz değer *R*ve Koşullu XOR maskesi *A*. BITS ham shift kaydının (değerleri tarafından tanımlanan bir bit karıştırma matris göre geliştirildiğinde) ek olarak, karıştırılmış *U*, *D*, *S*, *B* , *T*, *C*, ve *L*.

Şablon bağımsız değişkeni `UIntType` değerleri içerebilecek kadar büyük olmalıdır `2` <sup>W</sup> - `1`. Bir şablon bağımsız değişkenlerinin değerleri aşağıdaki gereksinimleri karşılaması gerekir: `2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`.

Doğrudan bu altyapısından bir oluşturucuyu oluşturmak olsa da, önceden tanımlanmış bu tür tanımlarından birini kullanmanız önerilir:

`mt19937`: 32-bit Mersenne bükücü altyapısı (Matsumoto ve Nishimura, 1998).

```cpp
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,
    31, 0x9908b0df,
    11, 0xffffffff,
    7, 0x9d2c5680,
    15, 0xefc60000,
    18, 1812433253> mt19937;
```

`mt19937_64`: 64 bit Mersenne bükücü altyapısı (Matsumoto ve Nishimura, 2000).

```cpp
typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,
    31, 0xb5026f5aa96619e9ULL,
    29, 0x5555555555555555ULL,
    17, 0x71d67fffeda60000ULL,
    37, 0xfff7eee000000000ULL,
    43, 6364136223846793005ULL> mt19937_64;
```

Mersenne bükücü algoritmasına hakkında ayrıntılı bilgi için bkz. Wikipedia makalesi [Mersenne bükücü](http://go.microsoft.com/fwlink/p/?linkid=402356).

## <a name="example"></a>Örnek

Kod örneği için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
