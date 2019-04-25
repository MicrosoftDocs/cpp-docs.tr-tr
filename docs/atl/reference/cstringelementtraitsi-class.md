---
title: Cstringelementtraitsı sınıfı
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
ms.openlocfilehash: 77357aa2be326ebebaaf5a8614faaf88a0c3c06b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277441"
---
# <a name="cstringelementtraitsi-class"></a>Cstringelementtraitsı sınıfı

Bu sınıf, koleksiyon sınıfı nesnelerini içinde depolanan dizeleri ilgili statik işlevler sağlar. Benzer [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), ancak büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStringElementTraitsI::CompareElements](#compareelements)|Farklar durumda yoksayılıyor eşitliği iki dize öğe Karşılaştırılacak statik bu işlevi çağırın.|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Farklar durumda yoksayılıyor iki dize öğe Karşılaştırılacak statik bu işlevi çağırın.|
|[CStringElementTraitsI::Hash](#hash)|Verilen dize öğesi için bir karma değeri hesaplamak için statik bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, dizeleri karşılaştırmak ve bir karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için koleksiyon sınıfı kullanıldığında yararlıdır. Kullanım [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) olduğunda dize nesneleri ile ile başvuru olarak ele alınabilir.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="compareelements"></a>  CStringElementTraitsI::CompareElements

Farklar durumda yoksayılıyor eşitliği iki dize öğe Karşılaştırılacak statik bu işlevi çağırın.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğe yanlış Aksi takdirde, eşitse true döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmalar büyük/küçük harfe duyarsızdır.

##  <a name="compareelementsordered"></a>  CStringElementTraitsI::CompareElementsOrdered

Farklar durumda yoksayılıyor iki dize öğe Karşılaştırılacak statik bu işlevi çağırın.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, < 0, *str1* olduğu küçüktür *str2*, veya > 0 ise *str1* büyüktür *str2*. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmalar yapmak için kullanılır.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmalar büyük/küçük harfe duyarsızdır.

##  <a name="hash"></a>  CStringElementTraitsI::Hash

Verilen dize öğesi için bir karma değeri hesaplamak için statik bu işlevi çağırın.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizenin içeriklerini kullanarak hesaplanan bir karma değer döndürür.

##  <a name="inargtype"></a>  CStringElementTraitsI::INARGTYPE

Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraitsI::OUTARGTYPE

Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase Sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CStringElementTraits Sınıfı](../../atl/reference/cstringelementtraits-class.md)
