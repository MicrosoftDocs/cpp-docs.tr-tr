---
title: decay Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::decay
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
ms.openlocfilehash: 73b9e2d8ef9a14830c13ee3f6566137bb51e939d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450637"
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

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri bir bağımsız değişken olarak geçirildikçe, sonuç türünü oluşturmak için Decay şablonunu kullanın. TypeDef `type` şablon sınıfı üyesi, aşağıdaki aşamalar içinde tanımlanan bir değiştirilmiş türü tutar:

- Türü `U` olarak`remove_reference<T>::type`tanımlanır.

- True ise, değiştirilen tür `type` olur `remove_extent<U>::type *`. `is_array<U>::value`

- Aksi halde, true ise, değiştirilen tür `type` olur `add_pointer<U>::type`. `is_function<U>::value`

- Aksi takdirde, değiştirilen tür `type` olur `remove_cv<U>::type`.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
