---
title: independent_bits_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: 8f420ca054d20cd222b8eda9a4a35a383a8e535a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635844"
---
# <a name="independentbitsengine-class"></a>independent_bits_engine Sınıfı

Kendi temel altyapısıyla döndürülen değerlerden bitleri repacking BITS kullanılarak belirtilen sayıda sayıların rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısı*<br/>
Temel altyapısı türü.

*W*<br/>
**Word boyutu**. Oluşturulan her bir sayının bit cinsinden boyutu. **Önkoşul**: `0 < W ≤ numeric_limits<UIntType>::digits`

*UIntType*<br/>
İşeritsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

Altyapısı üyeleri hakkında daha fazla bilgi için bkz. [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının açıklayan bir *altyapısı bağdaştırıcısı* değerler üreten sonuçta kendi temel altyapısıyla döndürülen değerlerden bitleri yeniden paketleyerek *W*-bit değerleri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
