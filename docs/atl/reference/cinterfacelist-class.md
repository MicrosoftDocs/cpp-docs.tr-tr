---
title: CInterfaceList Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 0a7fd781c63e4ea084cf078e49fc9efb9cfa2d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326786"
---
# <a name="cinterfacelist-class"></a>CInterfaceList Sınıfı

Bu sınıf, COM arabirim işaretçileri listesini yaparken yararlı yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Arabirim listesinin oluşturucusu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, COM arabirim işaretçileri listesini oluşturmak için bir oluşturucu ve türetilmiş yöntemler sağlar. Bir dizi gerektiğinde [CInterfaceArray'i](../../atl/reference/cinterfacearray-class.md) kullanın.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a>CInterfaceList::CInterfaceList

Arabirim listesinin oluşturucusu.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Varsayılan değer 10 olan blok boyutu.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlList Sınıfı](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr Sınıfı](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
