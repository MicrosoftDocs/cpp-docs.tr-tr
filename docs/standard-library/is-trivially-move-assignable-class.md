---
title: is_trivially_move_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1248c8efd06069863a9f78a94378fe7aed651011
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable sınıfı

Önemsiz taşıma atama işleci türüne sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir önemsiz taşıma atama işleci, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir taşıma atama işleci `Ty` deyimle varsa:

örtük olarak sağlanır

sınıf `Ty` hiçbir sanal işleve sahip

sınıf `Ty` hiçbir sanal temellerine sahip

sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma atama işleçleri sahip

sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma atama işleçleri sahip

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
