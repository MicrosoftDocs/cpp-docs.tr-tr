---
title: is_trivially_copy_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d63087e67996ae4836fba09baab4ebe1589e3465
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
