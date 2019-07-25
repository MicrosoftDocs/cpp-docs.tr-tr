---
title: mersenne_twister_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::mersenne_twister_engine
helpviewer_keywords:
- mersenne_twister_engine class
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
ms.openlocfilehash: ed5380e36e71d7366d2b4b84528bbd35b87cc775
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451855"
---
# <a name="mersennetwisterengine-class"></a>mersenne_twister_engine Sınıfı

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

*UIntType*\
İşaretsiz tamsayı sonuç türü. Olası türler için bkz [ \<. Random >](../standard-library/random.md).

*ANLATIMI*\
**Sözcük boyutu**. Durum sırasının bit cinsinden her bir sözcüğün boyutu. **Önkoşul**:`2u < W ≤ numeric_limits<UIntType>::digits`

*NO*\
**Durum boyutu**. Durum dizisindeki öğe sayısı (değerler).

*M*\
**Kaydırma boyutu**. Her bir twist sırasında atlanacak öğe sayısı. **Önkoşul**:`0 < M ≤ N`

*R*\
**Maske bitleri**. **Önkoşul**:`R ≤ W`

*A*\
**Xor maskesi**. **Önkoşul**:`A ≤ (1u<<W) - 1u`

*U*, *S*, *T*, *L*\
Alt **karakter değiştirme parametreleri**. Karıştırma sırasında (templing) kaydırma değeri olarak kullanılır. Koşul`U,S,T,L ≤ W`

*D*, *B*, *C*\
**Tempbıt bit maskesi parametreleri**. Karıştırma sırasında bit maskesi değerleri olarak kullanılır (templama). Koşul`D,B,C ≤ (1u<<W) - 1u`

*VADELİ*\
**Başlatma çarpanı**. Sıranın başlatılmasına yardımcı olmak için kullanılır. Koşul`F ≤ (1u<<W) - 1u`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|

`default_seed``5489u`, için`mersenne_twister_engine::seed` varsayılan parametre değeri olarak kullanılan, ve tek değer Oluşturucusu olarak tanımlanmış bir üye sabiti.

Altyapı üyeleri hakkında daha fazla bilgi için bkz [ \<. Random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu `0`şablon sınıfı, [, <sup></sup> -  `2`W`1`] kapalı aralığındaki değerleri döndüren rastgele bir sayı altyapısını açıklar. Bit ile `W * (N - 1) + R` büyük bir integral değeri tutar. Bu büyük değerden bir anda *W* bit ayıklar ve tüm bitleri kullandığınızda, kümeden Ayıklanacak yeni bir bit kümesine sahip olacak şekilde bitleri değiştirerek ve karıştırarak büyük bir değer elde eder. Altyapının durumu, en az *N* kez `N` çağrılmışsa kullanılan `operator()` son `W`bit değerlerdir; Aksi takdirde, `M` `W`kullanılan-bit değerleri ve en son `N - M` değerleri çekirdek.

Oluşturucu, çift yönlü bir geri bildirim, *N* ve *M*, bir oyundur değeri *R*ve bir koşullu XOR-Mask *a*ile tanımlanan bir çift yönlü geri bildirim kullanarak tuttuğu büyük değeri içerir. Ayrıca, ham kaydırma kaydının bitleri *U*, *D*, *S*, *B*, *T*, *C*ve *L*değerleri tarafından tanımlanan bir bit karıştırma matrisine göre karıştırılırdı (tempırılulmuş).

Şablon bağımsız değişkeni `UIntType` , `2`en fazla <sup>W</sup> - `1`değeri tutabilecek kadar büyük olmalıdır. Diğer şablon bağımsız değişkenlerinin değerlerinin aşağıdaki gereksinimleri karşılaması gerekir: `2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`.

Bu altyapıdan doğrudan bir Oluşturucu oluşturabilseniz de, önceden tanımlanmış aşağıdaki Typedefs değerlerinden birini kullanmanız önerilir:

`mt19937`: 32-bit Mersenne bükücü altyapısı (Matsumoto ve ndiimura, 1998).

```cpp
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,
    31, 0x9908b0df,
    11, 0xffffffff,
    7, 0x9d2c5680,
    15, 0xefc60000,
    18, 1812433253> mt19937;
```

`mt19937_64`: 64-bit Mersenne bükücü altyapısı (Matsumoto ve ndiimura, 2000).

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

Kod örneği için bkz [ \<. Random >](../standard-library/random.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<rastgele >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Rastgele >](../standard-library/random.md)
