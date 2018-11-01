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
ms.openlocfilehash: eaa21700f63ae07565dba4b8b3b5dabac69e0168
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553744"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrBase Sınıfı](../../atl/reference/cheapptrbase-class.md)<br/>
[CComAllocator Sınıfı](../../atl/reference/ccomallocator-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
