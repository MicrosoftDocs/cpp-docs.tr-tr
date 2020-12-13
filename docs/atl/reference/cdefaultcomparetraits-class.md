---
description: 'Daha fazla bilgi edinin: Cdefaultcomparetoyits sınıfı'
title: Cdefaultcomparetoyits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: dcb366cdcd99a6eed2b641be290ccc4913a81476
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141914"
---
# <a name="cdefaultcomparetraits-class"></a>Cdefaultcomparetoyits sınıfı

Bu sınıf varsayılan öğe karşılaştırma işlevlerini sağlar.

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
|[Cdefaultcomparetrayits:: CompareElements](#compareelements)|Se İki öğeyi eşitlik açısından karşılaştırmak için bu işlevi çağırın.|
|[Cdefaultcomparetoyits:: Compareelementsorimli](#compareelementsordered)|Se Daha büyük ve daha küçük öğeyi öğrenmek için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir koleksiyon sınıfı nesnesinde depolanan öğeleri karşılaştırmak için iki statik işlev içerir. Bu sınıf [Cdefaultelementnitelikler sınıfı](../../atl/reference/cdefaultelementtraits-class.md)tarafından kullanılır.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a> Cdefaultcomparetrayits:: CompareElements

İki öğeyi eşitlik açısından karşılaştırmak için bu işlevi çağırın.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametreler

*element1*<br/>
İlk öğesi.

*element2*<br/>
İkinci öğe.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması eşitlik ( **==** ) işleçtir. Basit veri türleri dışındaki nesneler için, bu işlevin geçersiz kılınabilmesi gerekebilir.

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a> Cdefaultcomparetoyits:: Compareelementsorimli

Daha büyük ve daha küçük öğeyi öğrenmek için bu işlevi çağırın.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametreler

*element1*<br/>
İlk öğesi.

*element2*<br/>
İkinci öğe.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki tabloya göre bir tamsayı döndürür:

|Koşul|Döndürülen değer|
|---------------|------------------|
|*Element1*  <  *element2*|<0|
|*Element1*  ==  *element2*|0|
|*Element1*  >  *element2*|>0|

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması **==** , **\<**, and **>** işleçlerini kullanır. Basit veri türleri dışındaki nesneler için, bu işlevin geçersiz kılınabilmesi gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
