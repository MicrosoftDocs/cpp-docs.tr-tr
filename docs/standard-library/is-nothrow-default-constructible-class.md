---
description: 'Hakkında daha fazla bilgi edinin: is_nothrow_default_constructible sınıfı'
title: is_nothrow_default_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
ms.openlocfilehash: bbfadf10048175472c10f264856cdb519896b65f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230802"
---
# <a name="is_nothrow_default_constructible-class"></a>is_nothrow_default_constructible Sınıfı

Türün oluşturma olmayan bir varsayılan oluşturucuya sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_nothrow_default_constructible;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür kümesi bir nothrow varsayılan *oluşturucusuna sahipse,* tür koşulunun bir örneği true, aksi takdirde false değerini taşır. Tür belirtiminin bir örneği değerine eşdeğerdir `is_nothrow_constructible<Ty>` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
