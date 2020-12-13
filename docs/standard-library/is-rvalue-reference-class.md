---
description: 'Hakkında daha fazla bilgi edinin: is_rvalue_reference sınıfı'
title: is_rvalue_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_rvalue_reference
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
ms.openlocfilehash: 1fb3de556f3a8b1b9aa70034a23e5e487336cd56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339033"
---
# <a name="is_rvalue_reference-class"></a>is_rvalue_reference Sınıfı

Türün bir rvalue başvurusu olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *Ty* bir [rvalue başvurusu](../cpp/rvalue-reference-declarator-amp-amp.md)ise, bu tür koşuldaki bir örnek true olarak tutulur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[Lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)
