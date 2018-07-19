---
title: decay sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5433c9ff76b8b6f218cfff5e5fd39a0ad7166613
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963621"
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

*T* değiştirilecek tür.

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
