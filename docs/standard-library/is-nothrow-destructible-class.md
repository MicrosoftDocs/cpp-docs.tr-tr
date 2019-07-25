---
title: is_nothrow_destructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 44de1f1fae1ea542aa247c0b39f04ee6bbd6308a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455898"
---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible sınıfı

Türün geri çevrilebilir olup olmadığını ve yıkıcının throw tarafından oluşturulup oluşturulmayacağını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* bir örneği, yeniden çevrilebilir bir tür ise ve yok edicinin oluşturmayabilmediği derleyici tarafından bilinir. Aksi takdirde, yanlış olur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
