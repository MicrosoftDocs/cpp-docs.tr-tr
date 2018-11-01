---
title: Ccomqıptrelementtraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: df1bbf5cb36e45b6b47acbd4263c34a7353fd6ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603742"
---
# <a name="ccomqiptrelementtraits-class"></a>Ccomqıptrelementtraits sınıfı

Bu sınıf, yöntem, statik işlevler ve tür tanımları yararlı COM arabirim işaretçilerini koleksiyonları oluştururken sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>Parametreler

*I*<br/>
Depolanacak işaretçi türü belirten bir COM arabirimi.

*piid*<br/>
Laboratuvardaki işaretçisi *miyim*.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf yöntemleri türetilir ve bir koleksiyon sınıfının oluştururken kullanışlı bir typedef sağlar [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM arabirimi işaretçisini nesneleri. Bu sınıf tarafından kullanılan [Cınterfacearray](../../atl/reference/cinterfacearray-class.md) ve [Cınterfacelist](../../atl/reference/cinterfacelist-class.md) sınıfları.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="inargtype"></a>  CComQIPtrElementTraits::INARGTYPE

Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>Ayrıca Bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
