---
description: 'Hakkında daha fazla bilgi edinin: is_nothrow_destructible sınıfı'
title: is_nothrow_destructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 017cc6de7ce5c618fcc3f47540efd34b5fdc40a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323624"
---
# <a name="is_nothrow_destructible-class"></a>is_nothrow_destructible sınıfı

Türün geri çevrilebilir olup olmadığını ve yıkıcının throw tarafından oluşturulup oluşturulmayacağını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* bir örneği, yeniden çevrilebilir bir tür ise ve yok edicinin oluşturmayabilmediği derleyici tarafından bilinir. Aksi takdirde, yanlış olur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
