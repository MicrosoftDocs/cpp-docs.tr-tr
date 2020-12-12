---
description: 'Daha fazla bilgi edinin: CSimpleArrayEqualHelperFalse sınıfı'
title: CSimpleArrayEqualHelperFalse sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 196f7873f72799408a629bc784cb343966801d79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140731"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse sınıfı

Bu sınıf [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı için yardımcı olur.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Türetilmiş bir sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse:: IsEqual](#isequal)|Se False döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı, sınıfı için bir tamamlayıcı `CSimpleArray` . Her zaman false döndürür ve buna ek olarak, `ATLASSERT` başvuruluyorsa yanlış bir bağımsız değişkenle çağracaktır. Eşitlik testinin yeterince tanımlanmadığı durumlarda bu sınıf, öğeleri içeren bir dizinin çoğu Yöntem için doğru şekilde çalışmasını sağlar, ancak [CSimpleArray:: Find](../../atl/reference/csimplearray-class.md#find)gibi karşılaştırmaları temel alan yöntemler için iyi tanımlanmış bir şekilde başarısız olur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpcoll. h

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelperFalse:: IsEqual

Yanlış değerini döndürür.

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>Dönüş Değeri

Yanlış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem her zaman false döndürür ve `ATLASSERT` başvuruluyorsa yanlış bir bağımsız değişkenle çağırır. , ' Nin amacı, `CSimpleArrayEqualHelperFalse::IsEqual` eşitlik testleri yeterince tanımlanmadığında iyi tanımlanmış bir biçimde başarısız olmak için karşılaştırmaları kullanarak yöntemleri zorlamaktır.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleArrayEqualHelper sınıfı](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
