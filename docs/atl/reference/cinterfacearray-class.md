---
title: Cınterfacearray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64b6266ac31e2d6dec6eabc847b67b080b250837
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751429"
---
# <a name="cinterfacearray-class"></a>Cınterfacearray sınıfı

Bu sınıf, bir COM arabirimi işaretçiler dizisi oluştururken kullanışlı yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Parametreler

*I*  
Depolanacak işaretçi türü belirten bir COM arabirimi.

*piid*  
Laboratuvardaki işaretçisi *miyim*.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Arabirimi dizi için oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir oluşturucu ve bir COM arabirimi işaretçiler dizisi oluşturmak için türetilmiş yöntemleri sağlar. Kullanım [Cınterfacelist](../../atl/reference/cinterfacelist-class.md) listesini zaman gereklidir.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="cinterfacearray"></a>  CInterfaceArray::CInterfaceArray

Oluşturucu.

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Akıllı işaretçi dizi başlatır.

## <a name="see-also"></a>Ayrıca Bkz.

[CAtlArray sınıfı](../../atl/reference/catlarray-class.md)   
[CComQIPtr sınıfı](../../atl/reference/ccomqiptr-class.md)   
[Ccomqıptrelementtraits sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
