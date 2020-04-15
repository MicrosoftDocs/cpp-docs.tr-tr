---
title: CStringElementTraitsI Sınıfı
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
ms.openlocfilehash: 32980e19443cb17a3a688c85ff21195c60ed2124
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330597"
---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI Sınıfı

Bu sınıf, koleksiyon sınıfı nesnelerinde depolanan dizeleri ile ilgili statik işlevler sağlar. [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)benzer, ancak büyük/küçük harf duyarsız karşılaştırmalar gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CstringElementTraitsI::CompareElements](#compareelements)|Bu statik işlevi, durum farklılıklarını göz ardı ederek eşitlik için iki dize öğesini karşılaştırmak için çağırın.|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|İki dize öğesini karşılaştırmak için bu statik işlevi çağırın, büyük/küçük harf farklılıklarını yok say.|
|[CStringElementTraitsI::Karma](#hash)|Verilen dize öğesi için karma değeri hesaplamak için bu statik işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf dizeleri karşılaştırmak ve karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için bir koleksiyon sınıfı kullanırken yararlıdır. Dize nesneleri başvuru olarak ele alınacaksa [CStringRefElementTraits'ı](../../atl/reference/cstringrefelementtraits-class.md) kullanın.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a>CstringElementTraitsI::CompareElements

Bu statik işlevi, durum farklılıklarını göz ardı ederek eşitlik için iki dize öğesini karşılaştırmak için çağırın.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmalar büyük/küçük harf duyarsızdır.

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraitsI::CompareElementsOrdered

İki dize öğesini karşılaştırmak için bu statik işlevi çağırın, büyük/küçük harf farklılıklarını yok say.

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

### <a name="remarks"></a>Açıklamalar

Karşılaştırmalar büyük/küçük harf duyarsızdır.

## <a name="cstringelementtraitsihash"></a><a name="hash"></a>CStringElementTraitsI::Karma

Verilen dize öğesi için karma değeri hesaplamak için bu statik işlevi çağırın.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dize içeriğini kullanarak hesaplanan karma değeri döndürür.

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a>CStringElementTraitsI::INARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a>CStringElementTraitsI::OUTARGTYPE

Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase Sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CStringElementTraits Sınıfı](../../atl/reference/cstringelementtraits-class.md)
