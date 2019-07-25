---
title: treat_as_floating_point Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 4cf3ac5be972d8636f1d3dbda3b195f4012517be
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459879"
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point Yapısı

Kayan nokta `Rep` türü olarak değerlendirilip değerlendirilmeyeceğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Açıklamalar

`Rep`yalnızca özelleşmenin `treat_as_floating_point<Rep>` [true_type](../standard-library/type-traits-typedefs.md#true_type)öğesinden türetildiği bir kayan nokta türü olarak değerlendirilebilir. Şablon sınıfı, Kullanıcı tanımlı bir tür için özelleştirilebilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<> hatası

**Ad alanı:** std:: hatası

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<> hatası](../standard-library/chrono.md)
