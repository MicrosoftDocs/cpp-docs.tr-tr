---
description: 'Daha fazla bilgi edinin: CComHeapPtr sınıfı'
title: CComHeapPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 18865923e86a2392260ab1e6dedde2f37b9b4ea3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146633"
---
# <a name="ccomheapptr-class"></a>CComHeapPtr sınıfı

Yığın işaretçilerini yönetmek için bir akıllı işaretçi sınıfı.

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

|Ad|Açıklama|
|----------|-----------------|
|[CComHeapPtr:: CComHeapPtr](#ccomheapptr)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

`CComHeapPtr` öğesinden türetilir `CHeapPtr` , ancak com yordamlarını kullanarak bellek ayırmak Için [Ccomayırıcı](../../atl/reference/ccomallocator-class.md) kullanır. Kullanılabilir yöntemler için [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a> CComHeapPtr:: CComHeapPtr

Oluşturucu.

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
Varolan bir `CComHeapPtr` nesnesi.

### <a name="remarks"></a>Açıklamalar

Yığın işaretçisi, isteğe bağlı olarak, mevcut bir nesne kullanılarak oluşturulabilir `CComHeapPtr` . Bu durumda, yeni `CComHeapPtr` nesne yeni işaretçi ve kaynakları yönetme sorumluluğunu kabul eder.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrBase sınıfı](../../atl/reference/cheapptrbase-class.md)<br/>
[Ccomayırıcı sınıfı](../../atl/reference/ccomallocator-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
