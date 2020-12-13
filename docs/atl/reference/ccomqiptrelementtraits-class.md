---
description: 'Daha fazla bilgi edinin: Ccomqiptrelementnitelikler sınıfı'
title: Ccomqıptrelementnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 9aa96c5b926263d6ed58125a28f5d0a12d8107d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142343"
---
# <a name="ccomqiptrelementtraits-class"></a>Ccomqıptrelementnitelikler sınıfı

Bu sınıf, COM arabirim işaretçilerinden oluşan koleksiyonlar oluştururken yararlı yöntemler, statik işlevler ve tür tanımları sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>Parametreler

*Kaydedemiyorum*<br/>
Depolanacak işaretçinin türünü belirten bir COM arabirimi.

*piıd*<br/>
*I*'nin IID 'sine yönelik bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[Ccomqıptrelementnitelikler:: ıNARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf yöntemleri türetiliyor ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) com Interface işaretçi nesneleri koleksiyon sınıfı oluştururken yararlı bir typedef sağlar. Bu sınıf hem [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) hem de [CInterfaceList](../../atl/reference/cinterfacelist-class.md) sınıfları tarafından kullanılır.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cdefaultcomparetoyits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[Cdefaultelementnitelikler](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a> Ccomqıptrelementnitelikler:: ıNARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[Cdefaultelementnitelikler sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
