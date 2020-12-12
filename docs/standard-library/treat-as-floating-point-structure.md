---
description: 'Daha fazla bilgi edinin: treat_as_floating_point yapısı'
title: treat_as_floating_point Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 498421d454de1e15ea52282665bcf9ae7d045946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169066"
---
# <a name="treat_as_floating_point-structure"></a>treat_as_floating_point Yapısı

`Rep`Kayan nokta türü olarak değerlendirilip değerlendirilmeyeceğini belirtir.

## <a name="syntax"></a>Syntax

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Açıklamalar

`Rep`yalnızca özelleşme true_type türetildiği zaman bir kayan nokta türü olarak değerlendirilebilir `treat_as_floating_point<Rep>` . [](../standard-library/type-traits-typedefs.md#true_type) Sınıf şablonu, Kullanıcı tanımlı bir tür için özelleştirilebilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<chrono>

**Ad alanı:** std:: hatası

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
