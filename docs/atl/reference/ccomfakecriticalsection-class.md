---
title: CComFakeCriticalSection Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
ms.openlocfilehash: 4a5b9ba3551397a9c3d59a343e9c6b55b1c1207e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327849"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection Sınıfı

Bu sınıf [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) ile aynı yöntemleri sağlar, ancak kritik bir bölüm sağlamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComFakeCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComFakeCriticalSection::Init](#init)|Kritik bir bölüm olmadığı için hiçbir şey yapmaz.|
|[CcomfakeCriticalSection::Lock](#lock)|Kritik bir bölüm olmadığı için hiçbir şey yapmaz.|
|[CcomfakeCriticalSection::terim](#term)|Kritik bir bölüm olmadığı için hiçbir şey yapmaz.|
|[CcomfakeCriticalSection::Unlock](#unlock)|Kritik bir bölüm olmadığı için hiçbir şey yapmaz.|

## <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection`[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)bulunan yöntemleri aynalar. Ancak, `CComFakeCriticalSection` kritik bir bölüm sağlamaz; bu nedenle, yöntemleri hiçbir şey yapmaz.

Genellikle, `CComFakeCriticalSection` bir `typedef` ad `AutoCriticalSection` veya `CriticalSection`. [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)kullanırken, `typedef` bu `CComFakeCriticalSection`isimlerin her ikisi de başvuru . [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)kullanırken, onlar referans [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) ve `CComCriticalSection`, sırasıyla.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a>CComFakeCriticalSection::Init

Kritik bir bölüm olmadığı için hiçbir şey yapmaz.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a>CcomfakeCriticalSection::Lock

Kritik bir bölüm olmadığı için hiçbir şey yapmaz.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a>CcomfakeCriticalSection::terim

Kritik bir bölüm olmadığı için hiçbir şey yapmaz.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a>CcomfakeCriticalSection::Unlock

Kritik bir bölüm olmadığı için hiçbir şey yapmaz.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
