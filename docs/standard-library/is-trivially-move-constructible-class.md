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
ms.openlocfilehash: 316ffdee4905ff8a35baef7137ff7f28a2846786
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958198"
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible sınıfı

Taşıma Oluşturucu türü, Önemsiz varsa testleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty* Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu Önemsiz taşıma oluşturucusu, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir taşıma Oluşturucusu *Ty* gereksizse, varsa:

örtük olarak bildirilen

Bu örtük bir bildirimi eşdeğer parametre türleri

sınıf *Ty* sahip sanal işlev yok

sınıf *Ty* hiçbir sanal temellere sahip

Geçici statik olmayan veri üyeleri sınıf yoktur

tüm doğrudan tabanları sınıfının *Ty* Önemsiz taşıma oluşturucuları sahip

Önemsiz taşıma oluşturucuları sınıfları sınıf türünün tüm statik olmayan veri üyelerinin olması

Önemsiz taşıma oluşturucuları sınıflarını dizi sınıf türünde tüm statik olmayan veri üyelerine sahip

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
