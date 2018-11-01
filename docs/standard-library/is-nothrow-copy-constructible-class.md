---
title: is_nothrow_copy_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_constructible
helpviewer_keywords:
- is_nothrow_copy_constructible
ms.assetid: f13a0bea-63b1-492a-9a45-d445df35c282
ms.openlocfilehash: 7682ce8fd8f127ac20a20fb0918e69d8c2d76947
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509636"
---
# <a name="isnothrowcopyconstructible-class"></a>is_nothrow_copy_constructible Sınıfı

Türüne sahip olup olmadığını test bir **nothrow** kopya Oluşturucusu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_nothrow_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu nothrow kopya Oluşturucu, aksi takdirde sahiptir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
