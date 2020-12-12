---
description: 'Hakkında daha fazla bilgi edinin: is_final sınıfı'
title: is_final sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_final
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
ms.openlocfilehash: 04660309205689e14200cb5d214ce5dc80efb88f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323747"
---
# <a name="is_final-class"></a>is_final sınıfı

Türün işaretlenmiş bir sınıf türü olup olmadığını sınar `final` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, işaretlenmiş bir sınıf türü ise true `final` , aksi takdirde false barındırır. *T* bir sınıf türü ise, bu bir tamamen türü olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[Son belirtici](../cpp/final-specifier.md)
