---
title: is_trivially_move_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4368fa2b88d22f0b07bc10bba4769d05375041
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible sınıfı

Önemsiz türündeyse testleri Oluşturucusu taşıyın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir önemsiz taşıma oluşturucusu, aksi durumda olan bir sınıftır.

Bir sınıf için bir taşıma oluşturucusuna `Ty` deyimle varsa:

örtülü olarak bildirilen

parametre türleri örtük bir bildirimi gereksinimlerine eşdeğer

sınıf `Ty` hiçbir sanal işleve sahip

sınıf `Ty` hiçbir sanal temellerine sahip

sınıfta hiç geçici olmayan statik veri üyeleri yok

tüm doğrudan taban sınıfının `Ty` Önemsiz taşıma oluşturucuları sahip

sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma oluşturucuları sahip

sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma oluşturucuları sahip

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
