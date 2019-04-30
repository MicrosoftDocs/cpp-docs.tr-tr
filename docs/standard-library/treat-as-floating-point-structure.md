---
title: treat_as_floating_point Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 1b7b58983032ee74ed3d88feb7325cd537e1cc2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411948"
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point Yapısı

Belirtir olup olmadığını `Rep` bir kayan nokta türü olarak ele alınabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Açıklamalar

`Rep` bir kayan nokta türü olarak davranılıp yalnızca özelleştirmesi `treat_as_floating_point<Rep>` türetilir [true_type](../standard-library/type-traits-typedefs.md#true_type). Şablon sınıfı, kullanıcı tanımlı bir tür için özelleştirilebilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
