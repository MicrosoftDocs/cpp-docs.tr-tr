---
title: is_trivially_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: b25d16658def4e3cf620ab707d2dabacb2620f33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435549"
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable sınıfı

Önemsiz taşıma atama işleci türünde olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

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
