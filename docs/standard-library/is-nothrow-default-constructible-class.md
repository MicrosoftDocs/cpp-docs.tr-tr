---
title: is_nothrow_default_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
ms.openlocfilehash: d635c8a06d3acc45d214dbe7cb1eb7800f56dc86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148490"
---
# <a name="isnothrowdefaultconstructible-class"></a>is_nothrow_default_constructible Sınıfı

Oluşturmayan bir varsayılan oluşturucu türüne sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_nothrow_default_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu nothrow varsayılan bir oluşturucu, aksi takdirde sahiptir. Bir tür koşulu örneğini eşdeğerdir `is_nothrow_constructible<Ty>`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
