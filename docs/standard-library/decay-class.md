---
title: decay Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::decay
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
ms.openlocfilehash: 23c2cff37e67e78ba68c37468c110d7a3725b785
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480307"
---
# <a name="decay-class"></a>decay Sınıfı

Türü, değer olarak geçilemez olarak oluşturur. Tür başvuru olmayan, sabit olmayan, geçici olmayan yapar veya bir işlev ya da bir dizi türü için tür işaretçisi yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Decay şablon türü bağımsız değişken olarak değere göre geçirildiyse olarak elde edilen türü kullanın. Şablon sınıfı üye typedef `type` aşağıdaki aşamalara tanımlanan bir değiştirilmiş türü tutar:

- Türü `U` olarak tanımlanan `remove_reference<T>::type`.

- Varsa `is_array<U>::value` true ise değiştirilen türü `type` olduğu `remove_extent<U>::type *`.

- Aksi takdirde `is_function<U>::value` true ise değiştirilen türü `type` olduğu `add_pointer<U>::type`.

- Aksi takdirde, değiştirilen türü `type` olduğu `remove_cv<U>::type`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
