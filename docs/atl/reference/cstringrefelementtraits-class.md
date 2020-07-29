---
title: Cstringrefelementnitelikler sınıfı
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
ms.openlocfilehash: 6fa8772033a5a82940cf30b2a73d6ea356269d67
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226561"
---
# <a name="cstringrefelementtraits-class"></a>Cstringrefelementnitelikler sınıfı

Bu sınıf, koleksiyon sınıfı nesnelerinde depolanan dizelerle ilişkili statik işlevler sağlar. Dize nesneleri başvuru olarak ele alınır.

## <a name="syntax"></a>Söz dizimi

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cstringrefelementnitelikler:: CompareElements](#compareelements)|İki dize öğesini eşitlik için karşılaştırmak için bu statik işlevi çağırın.|
|[Cstringrefelementnitelikler:: Compareelementsorimli](#compareelementsordered)|İki dize öğesini karşılaştırmak için bu statik işlevi çağırın.|
|[Cstringrefelementnitelikler:: Hash](#hash)|Verilen dize öğesi için bir karma değer hesaplamak üzere bu statik işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, dizeleri karşılaştırmak ve bir karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için bir koleksiyon sınıfı kullanırken faydalıdır. [Cstrıngelementnitelikler](../../atl/reference/cstringelementtraits-class.md) ve [Cstrıngelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md)'nin aksine `CStringRefElementTraits` `CString` bağımsız değişkenlerin başvuru olarak geçirilmesine neden olur **`const`** `CString&` .

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cstringrefelementtraitscompareelements"></a><a name="compareelements"></a>Cstringrefelementnitelikler:: CompareElements

İki dize öğesini eşitlik için karşılaştırmak için bu statik işlevi çağırın.

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>Parametreler

*element1*<br/>
İlk dize öğesi.

*element2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse true, değilse false döndürür.

## <a name="cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>Cstringrefelementnitelikler:: Compareelementsorimli

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

Dizeler aynıysa sıfır, *str1* < *0 ' dan*küçükse 0 veya *str1* *str2*büyükse 0 >. [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmaları gerçekleştirmek için kullanılır.

## <a name="cstringrefelementtraitshash"></a><a name="hash"></a>Cstringrefelementnitelikler:: Hash

Verilen dize öğesi için bir karma değer hesaplamak üzere bu statik işlevi çağırın.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
String öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizenin içeriği kullanılarak hesaplanan bir karma değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
