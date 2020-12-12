---
description: 'Hakkında daha fazla bilgi edinin: is_copy_assignable sınıfı'
title: is_copy_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_copy_assignable
helpviewer_keywords:
- is_copy_assignable
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
ms.openlocfilehash: f13752ce74f316f180fb874572efaf15d1c06c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323804"
---
# <a name="is_copy_assignable-class"></a>is_copy_assignable sınıfı

Tür, atamaya kopyalanıp kopyalanamayacağını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

*Tür değeri* , kopya atama operatörü olan bir sınıfdaysa, tür koşulunun bir örneği true, aksi takdirde false değerini taşır. İs_assignable eşdeğerdir \<Ty&, const Ty&> .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
