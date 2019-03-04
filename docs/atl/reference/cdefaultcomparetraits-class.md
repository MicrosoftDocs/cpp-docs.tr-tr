---
title: CDefaultCompareTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: c5f4ab3737838af11501c4a0f2037b57087939c9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273601"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits sınıfı

Bu sınıf, varsayılan öğe karşılaştırma işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Statik) Eşitlik için iki öğe karşılaştırmak için bu işlevi çağırın.|
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Statik) Büyük ve daha az öğe belirlemek için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir koleksiyon sınıfı nesnesinde saklanan öğe karşılaştırmak için iki statik işlevler içerir. Bu sınıf tarafından kullanılan [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md).

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="compareelements"></a>  CDefaultCompareTraits::CompareElements

Eşitlik için iki öğe karşılaştırmak için bu işlevi çağırın.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametreler

*element1*<br/>
İlk öğe.

*element2*<br/>
İkinci öğe.

### <a name="return-value"></a>Dönüş Değeri

Öğe yanlış Aksi takdirde, eşitse true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını eşitliği olan (**==**) işleci. Basit veri türleri dışındaki nesneler için bu işlev geçersiz kılınması gerekebilir.

##  <a name="compareelementsordered"></a>  CDefaultCompareTraits::CompareElementsOrdered

Büyük ve daha az öğe belirlemek için bu işlevi çağırın.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametreler

*element1*<br/>
İlk öğe.

*element2*<br/>
İkinci öğe.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki tabloyu temel alan bir tamsayı döndürür:

|Koşul|Dönüş değeri|
|---------------|------------------|
|*element1* < *element2*|<0|
|*element1* == *element2*|0|
|*element1* > *element2*|>0|

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını kullanan **==**, **\<**, ve **>** işleçleri. Basit veri türleri dışındaki nesneler için bu işlev geçersiz kılınması gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
