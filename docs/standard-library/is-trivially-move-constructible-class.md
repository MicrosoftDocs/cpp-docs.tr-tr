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
ms.openlocfilehash: 9ad5631fc5d689ccb6632ac230aebdaf40f18f80
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106489"
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible sınıfı

Taşıma Oluşturucu türü, Önemsiz varsa testleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

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
