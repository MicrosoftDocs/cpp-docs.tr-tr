---
title: decay Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::decay
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
ms.openlocfilehash: 3b22dfecb1162ce67a0d648197465115acb044ba
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688108"
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

*T* \
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri bir bağımsız değişken olarak geçirildikçe, sonuç türünü oluşturmak için Decay şablonunu kullanın. @No__t_0 sınıf şablonu üyesi, aşağıdaki aşamalarda tanımlanan bir değiştirilmiş türü tutar:

- @No__t_0 türü `remove_reference<T>::type` olarak tanımlanır.

- @No__t_0 true ise, değiştirilen tür `type` `remove_extent<U>::type *`.

- Aksi takdirde, `is_function<U>::value` true ise, değiştirilen tür `type` `add_pointer<U>::type`.

- Aksi takdirde, `type` değiştirilen tür `remove_cv<U>::type`.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
