---
title: CStringRefElementTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
ms.openlocfilehash: b4dd76b9592b255a1553be3ca7a249f58fb2672e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330581"
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits Sınıfı

Bu sınıf, koleksiyon sınıfı nesnelerinde depolanan dizeleri ile ilgili statik işlevler sağlar. Dize nesneleri başvuru olarak ele alınır.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStringrefElementTraits::CompareElements](#compareelements)|Eşitlik için iki dize öğesini karşılaştırmak için bu statik işlevi çağırın.|
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|İki dize öğesini karşılaştırmak için bu statik işlevi çağırın.|
|[CStringRefElementTraits::Karma](#hash)|Verilen dize öğesi için karma değeri hesaplamak için bu statik işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf dizeleri karşılaştırmak ve karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için bir koleksiyon sınıfı kullanırken yararlıdır. [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) ve [CStringElementTraitsaksine,](../../atl/reference/cstringelementtraitsi-class.md) `CStringRefElementTraits` `CString` **const** `CString&` referanslar olarak geçirilecek bağımsız değişkenler neden olur.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cstringrefelementtraitscompareelements"></a><a name="compareelements"></a>CStringrefElementTraits::CompareElements

Eşitlik için iki dize öğesini karşılaştırmak için bu statik işlevi çağırın.

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>Parametreler

*öğe1*<br/>
İlk dize öğesi.

*eleman2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse doğru döndürür, aksi takdirde yanlış.

## <a name="cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered

İki dize öğesini karşılaştırmak için bu statik işlevi çağırın.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri aynı ysa sıfır, *str1* str2'den küçükse 0 < veya *str1* *str2'den*büyükse 0'>. *str2* Karşılaştırmaları gerçekleştirmek için [CStringT::Karşılaştır](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi kullanılır.

## <a name="cstringrefelementtraitshash"></a><a name="hash"></a>CStringRefElementTraits::Karma

Verilen dize öğesi için karma değeri hesaplamak için bu statik işlevi çağırın.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dize içeriğini kullanarak hesaplanan karma değeri döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase Sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
