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
ms.openlocfilehash: e0793cc2010e2f2281e667ce21909227a55234da
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064205"
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

*I*<br/>
Depolanacak işaretçi türü belirten bir COM arabirimi.

*piid*<br/>
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

[CAtlArray Sınıfı](../../atl/reference/catlarray-class.md)<br/>
[CComQIPtr Sınıfı](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
