---
description: 'Daha fazla bilgi edinin: Cstrıngelementtraitsı sınıfı'
title: Cstrıngelementtraitsı sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 0a626677f4a62805933b2effb4811394626374a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140407"
---
# <a name="cstringelementtraitsi-class"></a>Cstrıngelementtraitsı sınıfı

Bu sınıf, koleksiyon sınıfı nesnelerinde depolanan dizelerle ilişkili statik işlevler sağlar. [Cstrıngelementnitelikler](../../atl/reference/cstringelementtraits-class.md)'e benzerdir, ancak büyük/küçük harfe duyarsız karşılaştırmalar gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[Cstrıngelementtraitsı:: ıNARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[Cstrıngelementtraitsı:: OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cstrıngelementtraitsı:: CompareElements](#compareelements)|İki dize öğesini eşitlik için karşılaştırmak üzere bu statik işlevi çağırın, ancak büyük/küçük harf farklılıkları yok sayılıyor.|
|[Cstrıngelementtraitsı:: Compareelementsorimli](#compareelementsordered)|Büyük/küçük harfli farklılıkları yoksayarak iki dize öğesini karşılaştırmak için bu statik işlevi çağırın.|
|[Cstrıngelementtraitsı:: Hash](#hash)|Verilen dize öğesi için bir karma değer hesaplamak üzere bu statik işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, dizeleri karşılaştırmak ve bir karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için bir koleksiyon sınıfı kullanırken faydalıdır. Dize nesneleri başvuru olarak ele alınır olduğunda [Cstringrefelementnitelikler](../../atl/reference/cstringrefelementtraits-class.md) kullanın.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a> Cstrıngelementtraitsı:: CompareElements

İki dize öğesini eşitlik için karşılaştırmak üzere bu statik işlevi çağırın, ancak büyük/küçük harf farklılıkları yok sayılıyor.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmalar büyük/küçük harfe duyarlıdır.

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a> Cstrıngelementtraitsı:: Compareelementsorimli

Büyük/küçük harfli farklılıkları yoksayarak iki dize öğesini karşılaştırmak için bu statik işlevi çağırın.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, *str1* < *0 ' dan* küçükse 0 veya *str1* *str2* büyükse 0 >. [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmaları gerçekleştirmek için kullanılır.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmalar büyük/küçük harfe duyarlıdır.

## <a name="cstringelementtraitsihash"></a><a name="hash"></a> Cstrıngelementtraitsı:: Hash

Verilen dize öğesi için bir karma değer hesaplamak üzere bu statik işlevi çağırın.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
String öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizenin içeriği kullanılarak hesaplanan bir karma değer döndürür.

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a> Cstrıngelementtraitsı:: ıNARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a> Cstrıngelementtraitsı:: OUTARGTYPE

Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Cstrıngelementnitelikler sınıfı](../../atl/reference/cstringelementtraits-class.md)
