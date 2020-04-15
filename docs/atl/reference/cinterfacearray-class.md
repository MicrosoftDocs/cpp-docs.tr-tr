---
title: CInterfaceArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: e6efe31989b06f0977ecff156a8f64053dc64ad1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326794"
---
# <a name="cinterfacearray-class"></a>CInterfaceArray Sınıfı

Bu sınıf, com arabirim işaretçileri bir dizi yaparken yararlı yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Parametreler

*Ⅰ*<br/>
Depolanacak işaretçi türünü belirten bir COM arabirimi.

*piid*<br/>
*IID*için bir işaretçi .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Arabirim dizisinin oluşturucusu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, com arabirim işaretçileri bir dizi oluşturmak için bir oluşturucu ve türetilmiş yöntemler sağlar. Bir liste gerektiğinde [CInterfaceList'i](../../atl/reference/cinterfacelist-class.md) kullanın.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cinterfacearraycinterfacearray"></a><a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray

Oluşturucu.

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Akıllı işaretçi dizisini başharfe alır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlArray Sınıfı](../../atl/reference/catlarray-class.md)<br/>
[CComQIPtr Sınıfı](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
