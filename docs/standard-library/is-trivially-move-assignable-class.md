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
ms.openlocfilehash: ae0db2b789e16a39396a329a64dfb8794eef5775
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961915"
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable sınıfı

Önemsiz taşıma atama işleci türünde olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty* Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu Önemsiz taşıma atama işleci, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir taşıma atama işlecini *Ty* gereksizse, varsa:

örtük olarak sağlanan

sınıf *Ty* sahip sanal işlev yok

sınıf *Ty* hiçbir sanal temellere sahip

tüm statik olmayan veri üyeleri sınıf türünün sınıflarını sahip Önemsiz taşıma atama işleçleri

Önemsiz taşıma atama işleçleri dizi sınıf türünde tüm statik olmayan veri üyelerinin sınıflarını sahip

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
