---
title: CSimpleArrayEqualHelper sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87b23ba46ee4a8e25c15b4d9e51b87c444da67f1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758221"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper sınıfı

Bu sınıf için Yardımcısı, [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template <class T>  
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Parametreler

`T`  
Türetilmiş bir sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statik) İki `CSimpleArray` nesne eşitliği öğeleri.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı için bir ektir `CSimpleArray` sınıfı. Depolanan karşılaştırma iki öğe için bir yöntem sağlar. bir `CSimpleArray` nesne. Varsayılan olarak, öğeleri kullanılarak karşılaştırılır **operator=()**, ancak dizi kendi eşitlik işleci eksik karmaşık veri türleri içeriyorsa, bu sınıf geçersiz kılmak gerekir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual

İki `CSimpleArray` nesne eşitliği öğeleri.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Parametreler

*T1*  
T türünde bir nesne

*T2*  
T türünde bir nesne

### <a name="return-value"></a>Dönüş Değeri

Öğe yanlış Aksi takdirde, eşitse true döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CSimpleArray sınıfı](../../atl/reference/csimplearray-class.md)   
[CSimpleArrayEqualHelperFalse sınıfı](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
