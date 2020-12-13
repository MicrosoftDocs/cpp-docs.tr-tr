---
description: 'Daha fazla bilgi edinin: CInterfaceArray sınıfı'
title: CInterfaceArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: 6dbe382682b8411d7562d1d0ff75f0ef587396f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141550"
---
# <a name="cinterfacearray-class"></a>CInterfaceArray sınıfı

Bu sınıf bir COM arabirim işaretçileri dizisi oluştururken yararlı yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceArray:: CInterfaceArray](#cinterfacearray)|Arabirim dizisi için Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir Oluşturucu ve bir COM arabirim işaretçileri dizisi oluşturmak için türetilmiş yöntemler sağlar. Bir liste gerektiğinde [CInterfaceList](../../atl/reference/cinterfacelist-class.md) kullanın.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cinterfacearraycinterfacearray"></a><a name="cinterfacearray"></a> CInterfaceArray:: CInterfaceArray

Oluşturucu.

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Akıllı işaretçi dizisini başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlArray sınıfı](../../atl/reference/catlarray-class.md)<br/>
[CComQIPtr sınıfı](../../atl/reference/ccomqiptr-class.md)<br/>
[Ccomqıptrelementnitelikler sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
