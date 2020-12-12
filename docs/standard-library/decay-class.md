---
description: 'Daha fazla bilgi edinin: Decay sınıfı'
title: decay Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::decay
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
ms.openlocfilehash: 6f6a1ebd31af44a48eaf400f9dccefdbd8ca3d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324607"
---
# <a name="decay-class"></a>decay Sınıfı

Türü değeri geçti olarak üretir. Tür başvurusu olmayan, const olmayan, geçici olmayan ya da bir işlevden veya dizi türünden tür işaretçisi yapmaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri bir bağımsız değişken olarak geçirildikçe, sonuç türünü oluşturmak için Decay şablonunu kullanın. Sınıf şablonu üyesi typedef, `type` aşağıdaki aşamalar içinde tanımlı bir değiştirilmiş türü tutar:

- Türü `U` olarak tanımlanır `remove_reference<T>::type` .

- `is_array<U>::value`True ise, değiştirilen tür `type` olur `remove_extent<U>::type *` .

- Aksi halde, `is_function<U>::value` true ise, değiştirilen tür `type` olur `add_pointer<U>::type` .

- Aksi takdirde, değiştirilen tür `type` olur `remove_cv<U>::type` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
