---
title: CComFakeCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48b120b7be3e605b6ed2619cbd71011b0a693bdc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757282"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection sınıfı

Bu sınıf olarak aynı yöntemler sağlar [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) ancak kritik bölüm sağlamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComFakeCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComFakeCriticalSection::Init](#init)|Kritik bölüm bu yana hiçbir şey yapmaz.|
|[CComFakeCriticalSection::Lock](#lock)|Kritik bölüm bu yana hiçbir şey yapmaz.|
|[CComFakeCriticalSection::Term](#term)|Kritik bölüm bu yana hiçbir şey yapmaz.|
|[CComFakeCriticalSection::Unlock](#unlock)|Kritik bölüm bu yana hiçbir şey yapmaz.|

## <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection` bulunan yöntemlerini yansıtan [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Ancak, `CComFakeCriticalSection` kritik bir bölüm; sağlamaz bu nedenle, metotlarını hiçbir şey yapma.

Genellikle, kullandığınız `CComFakeCriticalSection` aracılığıyla bir `typedef` name, ya da `AutoCriticalSection` veya `CriticalSection`. Kullanırken [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), bunların her ikisi de `typedef` başvuru adları `CComFakeCriticalSection`. Kullanırken [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), bunlar başvuru [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) ve `CComCriticalSection`sırasıyla.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="init"></a>  CComFakeCriticalSection::Init

Kritik bölüm bu yana hiçbir şey yapmaz.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

##  <a name="lock"></a>  CComFakeCriticalSection::Lock

Kritik bölüm bu yana hiçbir şey yapmaz.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

##  <a name="term"></a>  CComFakeCriticalSection::Term

Kritik bölüm bu yana hiçbir şey yapmaz.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock

Kritik bölüm bu yana hiçbir şey yapmaz.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
