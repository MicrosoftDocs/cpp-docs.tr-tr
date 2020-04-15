---
title: CComHeapPtr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 78cadfff9a278cf080393ab919f3891b201c91aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327772"
---
# <a name="ccomheapptr-class"></a>CComHeapPtr Sınıfı

Yığın işaretçileri yönetmek için akıllı bir işaretçi sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığında depolanacak nesne türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

`CComHeapPtr``CHeapPtr`türetilmiştir, ancak COM yordamları kullanarak bellek ayırmak için [CComAllocator](../../atl/reference/ccomallocator-class.md) kullanır. Mevcut yöntemler için [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CHeapPtrBase'e](../../atl/reference/cheapptrbase-class.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[Cheapptr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr

Oluşturucu.

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>Parametreler

*Pdata*<br/>
Varolan bir `CComHeapPtr` nesnesi.

### <a name="remarks"></a>Açıklamalar

Yığın işaretçisi isteğe bağlı `CComHeapPtr` olarak varolan bir nesne kullanılarak oluşturulabilir. Bu nedenle, `CComHeapPtr` yeni nesne yeni işaretçi ve kaynakları yönetmek için sorumluluk üstlenir.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrBase Sınıfı](../../atl/reference/cheapptrbase-class.md)<br/>
[CComAllocator Sınıfı](../../atl/reference/ccomallocator-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
