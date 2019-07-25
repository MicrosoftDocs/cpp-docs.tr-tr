---
title: independent_bits_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: a90e4be4ff6e92734f6b2e6804f8059be78e66b9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456350"
---
# <a name="independentbitsengine-class"></a>independent_bits_engine Sınıfı

Taban altyapısı tarafından döndürülen değerlerden bitleri yeniden paketleyerek, belirtilen sayıda bit içeren rastgele bir sayı dizisi üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısına*\
Temel altyapı türü.

*ANLATIMI*\
**Sözcük boyutu**. Oluşturulan her bir sayının bit cinsinden boyutu. **Önkoşul**:`0 < W ≤ numeric_limits<UIntType>::digits`

*UIntType*\
İşaretsiz tamsayı sonuç türü. Olası türler için bkz [ \<. Random >](../standard-library/random.md).

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

Altyapı üyeleri hakkında daha fazla bilgi için bkz [ \<. Random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfı, taban altyapısı tarafından döndürülen değerlerden bitleri yeniden paketleyerek değer üreten bir *altyapı bağdaştırıcısını* açıklar ve bu durum, *W*bit değerlerine neden olur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<rastgele >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Rastgele >](../standard-library/random.md)
