---
description: 'Daha fazla bilgi edinin: Cstrıngelementnitelikler sınıfı'
title: Cstrıngelementnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 1e3f6a73e71530250d9dd88408165471028a18e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140497"
---
# <a name="cstringelementtraits-class"></a>Cstrıngelementnitelikler sınıfı

Bu sınıf, nesneleri depolayan koleksiyon sınıfları tarafından kullanılan statik işlevler sağlar `CString` .

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[Cstrıngelementnitelikler:: ıNARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[Cstrıngelementnitelikler:: OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cstrıngelementnitelikler:: CompareElements](#compareelements)|Se İki dize öğesini eşitlik için karşılaştırmak için bu işlevi çağırın.|
|[Cstrıngelementnitelikler:: Compareelementsorimli](#compareelementsordered)|Se İki dize öğesini karşılaştırmak için bu işlevi çağırın.|
|[Cstrıngelementnitelikler:: CopyElements](#copyelements)|Se `CString` Bir koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu işlevi çağırın.|
|[Cstrıngelementnitelikler:: Hash](#hash)|Se Verilen dize öğesi için bir karma değer hesaplamak üzere bu işlevi çağırın.|
|[Cstrıngelementnitelikler:: Relocateöğeleri](#relocateelements)|Se `CString` Bir koleksiyon sınıfı nesnesinde depolanan öğelerin konumunu değiştirmek için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf dizeleri kopyalamak, taşımak ve karşılaştırmak için statik işlevler ve bir karma değer oluşturmak için sağlar. Bu işlevler, dize tabanlı verileri depolamak için bir koleksiyon sınıfı kullanırken faydalıdır. Büyük/küçük harfe duyarsız karşılaştırmalar gerektiğinde [Cstrıngelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md) kullanın. Dize nesneleri başvuru olarak ele alırken [Cstringrefelementnitelikler](../../atl/reference/cstringrefelementtraits-class.md) kullanın.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** CStringT. h

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a> Cstrıngelementnitelikler:: CompareElements

İki dize öğesini eşitlik için karşılaştırmak için bu statik işlevi çağırın.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse true, değilse false döndürür.

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a> Cstrıngelementnitelikler:: Compareelementsorimli

İki dize öğesini karşılaştırmak için bu statik işlevi çağırın.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, *str1* < *0 ' dan* küçükse 0 veya *str1* *str2* büyükse 0 >. [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmaları gerçekleştirmek için kullanılır.

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a> Cstrıngelementnitelikler:: CopyElements

`CString`Bir koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu statik işlevi çağırın.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Kopyalanmış verileri alacak olan ilk öğe işaretçisi.

*pSrc*<br/>
Kopyalanacak ilk öğe için işaretçi.

*nElements*<br/>
Kopyalanacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef öğeler çakışmamalıdır.

## <a name="cstringelementtraitshash"></a><a name="hash"></a> Cstrıngelementnitelikler:: Hash

Verilen dize öğesi için bir karma değer hesaplamak üzere bu statik işlevi çağırın.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
String öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizenin içeriği kullanılarak hesaplanan bir karma değer döndürür.

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a> Cstrıngelementnitelikler:: ıNARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a> Cstrıngelementnitelikler:: OUTARGTYPE

Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a> Cstrıngelementnitelikler:: Relocateöğeleri

`CString`Bir koleksiyon sınıfı nesnesinde depolanan öğelerin konumunu değiştirmek için bu statik işlevi çağırın.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Yeniden konumlandırılan verileri alacak olan ilk öğe işaretçisi.

*pSrc*<br/>
Yeniden konumlandırmak için ilk öğe işaretçisi.

*nElements*<br/>
Yeniden konumlandırmak için öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev, çoğu veri türü için yeterli olan [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)öğesini çağırır. Taşınan nesneler kendi üyelerine işaretçiler içeriyorsa, bu statik işlevin geçersiz kılınması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[Cstrıngelementtraitsı sınıfı](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
