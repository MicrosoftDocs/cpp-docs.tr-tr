---
title: CComHeapPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: ace8dbb174bd6585e61bd941a60dad28296af72a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246385"
---
# <a name="ccomheapptr-class"></a>CComHeapPtr sınıfı

Yığın işaretçileri yönetmek için bir akıllı işaretçi sınıfının.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığın üzerinde depolanan nesne türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

`CComHeapPtr` öğesinden türetilen `CHeapPtr`, ancak kullandığı [CComAllocator](../../atl/reference/ccomallocator-class.md) COM yordamları kullanarak bellek ayrılamadı. Bkz: [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) uygun olan yöntemler için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="ccomheapptr"></a>  CComHeapPtr::CComHeapPtr

Oluşturucu.

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
Varolan bir `CComHeapPtr` nesnesi.

### <a name="remarks"></a>Açıklamalar

Yığın işaretçisi isteğe bağlı olarak var olan bir oluşturulabilir `CComHeapPtr` nesne. Bu durumda, yeni `CComHeapPtr` nesne yeni işaretçi ve kaynaklarını yönetme sorumluluğunu varsayar.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrBase Sınıfı](../../atl/reference/cheapptrbase-class.md)<br/>
[CComAllocator Sınıfı](../../atl/reference/ccomallocator-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
