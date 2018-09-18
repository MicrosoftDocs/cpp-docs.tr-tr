---
title: Cınterfacelist sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac378e0a923e2a906bf99995432bfc87e39b8d5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032438"
---
# <a name="cinterfacelist-class"></a>Cınterfacelist sınıfı

Bu sınıf, COM arabirim işaretçilerini listesini oluştururken kullanışlı yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Arabirim listesi için oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir oluşturucu ve COM arabirim işaretçilerini listesini oluşturmak için türetilmiş yöntemleri sağlar. Kullanım [Cınterfacearray](../../atl/reference/cinterfacearray-class.md) bir dizi olduğunda gereklidir.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="cinterfacelist"></a>  CInterfaceList::CInterfaceList

Arabirim listesi için oluşturucu.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Varsayılan değer 10 blok boyutu.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[CAtlList Sınıfı](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr Sınıfı](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
