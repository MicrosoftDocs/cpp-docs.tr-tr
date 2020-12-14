---
description: 'Hakkında daha fazla bilgi edinin: is_trivial sınıfı'
title: is_trivial sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivial
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
ms.openlocfilehash: 56e5a3c915893b88228f4a40307d2c1e3c32555d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247663"
---
# <a name="is_trivial-class"></a>is_trivial sınıfı

Türün önemsiz bir tür olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür olarak bir örnek, tür *T* önemsiz bir tür ise true, aksi takdirde false barındırır. Önemsiz türler skaler türlerdir, Üçlü kopyalanabilir sınıf türleridir, bu türlerin dizileri ve bu türlerin CV nitelikli sürümleridir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
