---
title: CComQIPtrElementTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 19f2669c157310be02f746672b22f6c0ed005075
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327405"
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits Sınıfı

Bu sınıf yöntemleri, statik işlevleri sağlar ve COM arabirim işaretçileri koleksiyonları oluştururken yararlı typedefs.

## <a name="syntax"></a>Sözdizimi

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>Parametreler

*Ⅰ*<br/>
Depolanacak işaretçi türünü belirten bir COM arabirimi.

*piid*<br/>
*IID*için bir işaretçi .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CComQIPtrElementÖzellikleri::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf yöntemleri türetilmiştir ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM arabirim işaretçisi nesnelerinbir toplama sınıfı oluştururken yararlı bir typedef sağlar. Bu sınıf hem [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) hem de [CInterfaceList](../../atl/reference/cinterfacelist-class.md) sınıfları tarafından kullanılır.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CDefaultCompareÖzellikler](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a>CComQIPtrElementÖzellikleri::INARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
