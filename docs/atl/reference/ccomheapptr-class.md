---
title: CComHeapPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs:
- C++
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7a5b30ca507387b1529c9e9726e48735c844fac
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764835"
---
# <a name="ccomheapptr-class"></a>CComHeapPtr sınıfı

Yığın işaretçileri yönetmek için bir akıllı işaretçi sınıfının.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>Parametreler

*T*  
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

*pData*  
Varolan bir `CComHeapPtr` nesnesi.

### <a name="remarks"></a>Açıklamalar

Yığın işaretçisi isteğe bağlı olarak var olan bir oluşturulabilir `CComHeapPtr` nesne. Bu durumda, yeni `CComHeapPtr` nesne yeni işaretçi ve kaynaklarını yönetme sorumluluğunu varsayar.

## <a name="see-also"></a>Ayrıca Bkz.

[CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)   
[CHeapPtrBase sınıfı](../../atl/reference/cheapptrbase-class.md)   
[CComAllocator sınıfı](../../atl/reference/ccomallocator-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
