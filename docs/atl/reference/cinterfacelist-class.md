---
title: Cınterfacelist sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: e740d891e279bb29eeef898de52698dc3f04fc67
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258643"
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

## <a name="see-also"></a>Ayrıca bkz.

[CAtlList Sınıfı](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr Sınıfı](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
