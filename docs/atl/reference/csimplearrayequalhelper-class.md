---
description: 'Daha fazla bilgi edinin: CSimpleArrayEqualHelper sınıfı'
title: CSimpleArrayEqualHelper sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: e1a5fd3eea5fd6ef7563febc662c5a7a1bc639c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140770"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper sınıfı

Bu sınıf [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı için yardımcı olur.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Türetilmiş bir sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleArrayEqualHelper:: IsEqual](#isequal)|Se `CSimpleArray` Eşitlik için iki nesne öğesini sınar.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı, sınıfına bir ektir `CSimpleArray` . Bir nesnesinde depolanan iki öğeyi karşılaştırmak için bir yöntem sağlar `CSimpleArray` . Varsayılan olarak, öğeler **operator = ()** kullanılarak karşılaştırılır, ancak dizi kendi eşitlik operatörünün olmadığı karmaşık veri türleri içeriyorsa, bu sınıfı geçersiz kılmanız gerekir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpcoll. h

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelper:: IsEqual

`CSimpleArray`Eşitlik için iki nesne öğesini sınar.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
T türünde bir nesne.

*T2*<br/>
T türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse true, değilse false döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleArray sınıfı](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse sınıfı](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
