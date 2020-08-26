---
title: independent_bits_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: f9c1c97795e6d4eeff64ba8be8f22602f4f3fbd6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845776"
---
# <a name="independent_bits_engine-class"></a>independent_bits_engine Sınıfı

Taban altyapısı tarafından döndürülen değerlerden bitleri yeniden paketleyerek, belirtilen sayıda bit içeren rastgele bir sayı dizisi üretir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısına*\
Temel altyapı türü.

*Anlatımı*\
**Sözcük boyutu**. Oluşturulan her bir sayının bit cinsinden boyutu. **Önkoşul**: `0 < W ≤ numeric_limits<UIntType>::digits`

*UIntType*\
İşaretsiz tamsayı sonuç türü. Olası türler için bkz [\<random>](../standard-library/random.md) ..

## <a name="members"></a>Üyeler

`independent_bits_engine::independent_bits_engine`\
`independent_bits_engine::base`\
`independent_bits_engine::base_type`\
`independent_bits_engine::discard`\
`independent_bits_engine::operator()`\
`independent_bits_engine::seed`

Altyapı üyeleri hakkında daha fazla bilgi için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, taban altyapısı tarafından döndürülen değerlerden bitleri yeniden paketleyerek değer üreten bir *altyapı bağdaştırıcısını* açıklar ve bu durum, *W*bit değerlerine neden olur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
