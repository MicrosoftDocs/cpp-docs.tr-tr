---
title: CSimpleArrayEqualHelperFalse sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 35207fdcbffc0e0367d86682b5f731eef617d761
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269064"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse sınıfı

Bu sınıf için Yardımcısı, [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı.

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
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Statik) Yanlış değerini döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikleri tamamlayan bir sınıftır `CSimpleArray` sınıfı. Her zaman BT döndürür false değerini ve ayrıca, çağıracaktır `ATLASSERT` bağımsız hiç olmadığı kadar başvurulan yoksa false. Burada eşitlik testi yeterince tanımlı değil durumlarda, bu sınıf için çoğu yöntemleri doğru şekilde çalışmaz, ancak üzerinde karşılaştırmalar gibi bağlı yöntemler için iyi tanımlanmış bir şekilde başarısız için öğeleri içeren bir dizi sağlar [CSimpleArray:: Bulma](../../atl/reference/csimplearray-class.md#find).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelperFalse::IsEqual

Yanlış değerini döndürür.

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>Dönüş Değeri

Yanlış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem her zaman false değerini döndürür ve çağıracak `ATLASSERT` bağımsız başvurulan yoksa false. Amacı `CSimpleArrayEqualHelperFalse::IsEqual` yöntemleri karşılaştırmalar eşitliği testleri yeterince tanımlanmamış iyi tanımlanmış bir şekilde başarısız kullanmayı zorlamak için.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleArrayEqualHelper Sınıfı](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
