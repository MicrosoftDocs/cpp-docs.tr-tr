---
title: is_lvalue_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_lvalue_reference
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
ms.openlocfilehash: 5bcd5c8333f011475cb11a452759c8986ab22215
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456200"
---
# <a name="islvaluereference-class"></a>is_lvalue_reference Sınıfı

Türün bir lvalue başvurusu olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *Ty* bir nesneye veya işleve başvuru ise, bu tür koşuldaki bir örnek true, aksi takdirde false barındırır. *Ty* 'nin bir rvalue başvurusu olabileceğini unutmayın. Rvalues hakkında daha fazla bilgi için bkz. [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[Lvalue ve Rvalue’lar](../cpp/lvalues-and-rvalues-visual-cpp.md)
