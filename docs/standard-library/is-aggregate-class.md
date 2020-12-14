---
description: 'Hakkında daha fazla bilgi edinin: is_aggregate sınıfı'
title: is_aggregate sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_aggregate
helpviewer_keywords:
- is_aggregate
ms.openlocfilehash: 6ca27e6edea42b6c0ae3f0c89749a586adac857b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231374"
---
# <a name="is_aggregate-class"></a>is_aggregate sınıfı

Türün işaretlenmiş bir sınıf türü olup olmadığını sınar `aggregate` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_aggregate;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, işaretlenmiş bir sınıf türü ise true `aggregate` , aksi takdirde false barındırır. *T* bir sınıf türü ise, bu bir tamamen türü olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
