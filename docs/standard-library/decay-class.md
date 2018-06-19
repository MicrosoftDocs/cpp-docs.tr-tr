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
ms.openlocfilehash: e0451b8565a4d021181d79d15437637e1b2f3b27
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841804"
---
# <a name="decay-class"></a>decay Sınıfı

Değere göre geçti olarak türü üretir. Yaptığında türü başvuru olmayan, sabit olmayan geçici olmayan ya da bir işaretçi bir işlev veya bir dizi türü türe yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>Parametreler

`T` Değişiklik türü.

## <a name="remarks"></a>Açıklamalar

Decay şablon türü değer bağımsız değişken olarak geçirilen gibi sonuç türü oluşturmak için kullanın. Şablon sınıfının üye typedef `type` bulunan aşağıdaki aşamaları tanımlanan değiştirilmiş bir türü bulunur:

- Türü `U` olarak tanımlanan `remove_reference<T>::type`.

- Varsa `is_array<U>::value` doğrudur değiştirilmiş türü `type` olan `remove_extent<U>::type *`.

- Aksi halde, eğer `is_function<U>::value` doğrudur değiştirilmiş türü `type` olan `add_pointer<U>::type`.

- Aksi takdirde, değiştirilmiş türü `type` olan `remove_cv<U>::type`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
