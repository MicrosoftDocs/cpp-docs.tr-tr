---
title: is_trivially_copy_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c36808d375dd774286c3663a02fdc308cc4b2790
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857512"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable sınıfı

Türü bir önemsiz copy atama işleci olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` false tuttuğu bir önemsiz copy atama işleci, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir atama Oluşturucusu `T` , örtük olarak sağlanır, sınıf deyimle `T` sınıfı hiçbir sanal işleve sahip `T` hiçbir sanal temellerine sahip, sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz sahip atama işleçleri ve sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz atama işleçleri sahiptir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
