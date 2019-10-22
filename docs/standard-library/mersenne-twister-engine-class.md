---
title: mersenne_twister_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::mersenne_twister_engine
helpviewer_keywords:
- mersenne_twister_engine class
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
ms.openlocfilehash: 79613c76b3ea6dc15643e83a15d5bd6d90b60c6a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687698"
---
# <a name="mersenne_twister_engine-class"></a>mersenne_twister_engine Sınıfı

Mersenne bükücü algoritmasını temel alarak yüksek kaliteli rastgele tamsayılar dizisi oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class UIntType,
    size_t W, size_t N, size_t M, size_t R,
    UIntType A, size_t U, UIntType D, size_t S,
    UIntType B, size_t T, UIntType C, size_t L, UIntType F>
class mersenne_twister_engine;
```

### <a name="parameters"></a>Parametreler

*Uinttype* \
İşaretsiz tamsayı sonuç türü. Olası türler için bkz. [\<random >](../standard-library/random.md).

*W* \
**Sözcük boyutu**. Durum sırasının bit cinsinden her bir sözcüğün boyutu. **Önkoşul**: `2u < W ≤ numeric_limits<UIntType>::digits`

*N* \
**Durum boyutu**. Durum dizisindeki öğe sayısı (değerler).

*A* \
**Kaydırma boyutu**. Her bir twist sırasında atlanacak öğe sayısı. **Önkoşul**: `0 < M ≤ N`

*R* \
**Maske bitleri**. **Önkoşul**: `R ≤ W`

*Bir* \
**Xor maskesi**. **Önkoşul**: `A ≤ (1u<<W) - 1u`

*U*, *S*, *T*, *L* \
Alt **karakter değiştirme parametreleri**. Karıştırma sırasında (templing) kaydırma değeri olarak kullanılır. Önkoşul: `U,S,T,L ≤ W`

*D*, *B*, *C* \
**Tempbıt bit maskesi parametreleri**. Karıştırma sırasında bit maskesi değerleri olarak kullanılır (templama). Önkoşul: `D,B,C ≤ (1u<<W) - 1u`

*F* \
**Başlatma çarpanı**. Sıranın başlatılmasına yardımcı olmak için kullanılır. Önkoşul: `F ≤ (1u<<W) - 1u`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|

`default_seed`, `mersenne_twister_engine::seed` ve tek değer Oluşturucusu için varsayılan parametre değeri olarak kullanılan `5489u` olarak tanımlanan bir üye sabitidir.

Altyapı üyeleri hakkında daha fazla bilgi için bkz. [\<random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, [`0` `2`<sup>W</sup>  -  `1`] kapalı aralığındaki değerleri döndüren rastgele bir sayı altyapısını açıklar. @No__t_0 bitleri olan büyük bir integral değeri barındırır. Bu büyük değerden bir anda *W* bit ayıklar ve tüm bitleri kullandığınızda, kümeden Ayıklanacak yeni bir bit kümesine sahip olacak şekilde bitleri değiştirerek ve karıştırarak büyük bir değer elde eder. Altyapının durumu, `operator()` en az *N* kez çağrılmışsa kullanılan son `N` `W` bit değerlerdir, aksi takdirde kullanılan `M` `W` bit değerleri ve temel değerin son `N - M` değerleri.

Oluşturucu, çift yönlü bir geri bildirim, *N* ve *M*, bir oyundur değeri *R*ve bir koşullu XOR-Mask *a*ile tanımlanan bir çift yönlü geri bildirim kullanarak tuttuğu büyük değeri içerir. Ayrıca, ham kaydırma kaydının bitleri *U*, *D*, *S*, *B*, *T*, *C*ve *L*değerleri tarafından tanımlanan bir bit karıştırma matrisine göre karıştırılırdı (tempırılulmuş).

@No__t_0 şablon bağımsız değişkeni, değerleri `2`<sup>W</sup>  -  `1` tutabilecek kadar büyük olmalıdır. Diğer şablon bağımsız değişkenlerinin değerlerinin aşağıdaki gereksinimleri karşılaması gerekir: `2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`.

Bu altyapıdan doğrudan bir Oluşturucu oluşturabilseniz de, önceden tanımlanmış aşağıdaki Typedefs değerlerinden birini kullanmanız önerilir:

`mt19937`:32-bit Mersenne bükücü altyapısı (Matsumoto ve ndiimura, 1998).

```cpp
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,
    31, 0x9908b0df,
    11, 0xffffffff,
    7, 0x9d2c5680,
    15, 0xefc60000,
    18, 1812433253> mt19937;
```

`mt19937_64`:64-bit Mersenne bükücü altyapısı (Matsumoto ve ndiimura, 2000).

```cpp
typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,
    31, 0xb5026f5aa96619e9ULL,
    29, 0x5555555555555555ULL,
    17, 0x71d67fffeda60000ULL,
    37, 0xfff7eee000000000ULL,
    43, 6364136223846793005ULL> mt19937_64;
```

Mersenne twme algoritması hakkında ayrıntılı bilgi için, bkz. Vikipedi makalesi [Mersenne bükücü](https://go.microsoft.com/fwlink/p/?linkid=402356).

## <a name="example"></a>Örnek

Kod örneği için bkz. [\<random >](../standard-library/random.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<random >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random >](../standard-library/random.md)
