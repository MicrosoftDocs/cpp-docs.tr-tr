---
title: treat_as_floating_point Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: add69179b23a953a937458cbfa55254b21c5ea37
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685107"
---
# <a name="treat_as_floating_point-structure"></a>treat_as_floating_point Yapısı

@No__t_0, kayan nokta türü olarak değerlendirileceğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Açıklamalar

`Rep`, yalnızca özelleştirme `treat_as_floating_point<Rep>` [true_type](../standard-library/type-traits-typedefs.md#true_type)öğesinden türetildiği zaman bir kayan nokta türü olarak ele alınabilir. Sınıf şablonu, Kullanıcı tanımlı bir tür için özelleştirilebilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<chrono >

**Ad alanı:** std:: hatası

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[\<chrono >](../standard-library/chrono.md)
