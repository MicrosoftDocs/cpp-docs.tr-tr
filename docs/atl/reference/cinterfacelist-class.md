---
description: 'Daha fazla bilgi edinin: CInterfaceList sınıfı'
title: CInterfaceList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 2612ba4700466bb877f84978c55bfd018f1dd286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141537"
---
# <a name="cinterfacelist-class"></a>CInterfaceList sınıfı

Bu sınıf, COM arabirim işaretçilerinin bir listesini oluştururken yararlı yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Parametreler

*Kaydedemiyorum*<br/>
Depolanacak işaretçinin türünü belirten bir COM arabirimi.

*piıd*<br/>
*I*'nin IID 'sine yönelik bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInterfaceList:: CInterfaceList](#cinterfacelist)|Arabirim listesi için Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir Oluşturucu ve bir COM arabirim işaretçileri listesi oluşturmak için türetilmiş yöntemler sağlar. Bir dizi gerekliyse [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) kullanın.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a> CInterfaceList:: CInterfaceList

Arabirim listesi için Oluşturucu.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu, varsayılan olarak 10 ' dur.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının bir ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlList sınıfı](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr sınıfı](../../atl/reference/ccomqiptr-class.md)<br/>
[Ccomqıptrelementnitelikler sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
