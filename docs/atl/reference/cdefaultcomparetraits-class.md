---
title: CDefaultCompareTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: 8262800ef613424c37c53931d97dd4b1b1a71321
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327070"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits Sınıfı

Bu sınıf varsayılan öğe karşılaştırma işlevleri sağlar.

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

|Adı|Açıklama|
|----------|-----------------|
|[CDefaultCompareÖzellikler::Öğeleri Karşılaştır](#compareelements)|(Statik) Eşitlik için iki öğeyi karşılaştırmak için bu işlevi arayın.|
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Statik) Daha büyük ve daha küçük öğeyi belirlemek için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir koleksiyon sınıfı nesnesinde depolanan öğeleri karşılaştırmak için iki statik işlev içerir. Bu sınıf [CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)tarafından kullanılır.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a>CDefaultCompareÖzellikler::Öğeleri Karşılaştır

Eşitlik için iki öğeyi karşılaştırmak için bu işlevi arayın.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametreler

*öğe1*<br/>
İlk element.

*eleman2*<br/>
İkinci element.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması eşitlik**==**( ) işlecidir. Basit veri türleri dışındaki nesneler için bu işlevin geçersiz kılınması gerekebilir.

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered

Daha büyük ve daha küçük öğeyi belirlemek için bu işlevi çağırın.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametreler

*öğe1*<br/>
İlk element.

*eleman2*<br/>
İkinci element.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki tabloya göre bir sonda döndürür:

|Koşul|Döndürülen değer|
|---------------|------------------|
|*element1* < *element2*|<0|
|*element1* == *element2*|0|
|*element1* > *element2*|>0|

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması **==** **\<**, **>** ve işleçleri kullanır. Basit veri türleri dışındaki nesneler için bu işlevin geçersiz kılınması gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
