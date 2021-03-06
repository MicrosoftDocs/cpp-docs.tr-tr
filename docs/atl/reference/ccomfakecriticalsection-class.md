---
description: 'Daha fazla bilgi edinin: CComFakeCriticalSection Class'
title: CComFakeCriticalSection sınıfı
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
ms.openlocfilehash: 7280a47daa7464b24246ca8baa0aa7f5eaefa87a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152067"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection sınıfı

Bu sınıf [Ccomkritiksection](../../atl/reference/ccomcriticalsection-class.md) ile aynı yöntemleri sağlar ancak kritik bir bölüm sağlamaz.

## <a name="syntax"></a>Syntax

```
class CComFakeCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComFakeCriticalSection:: Init](#init)|Kritik bölüm olmadığından hiçbir şey yapmaz.|
|[CComFakeCriticalSection:: Lock](#lock)|Kritik bölüm olmadığından hiçbir şey yapmaz.|
|[CComFakeCriticalSection:: Term](#term)|Kritik bölüm olmadığından hiçbir şey yapmaz.|
|[CComFakeCriticalSection:: unlock](#unlock)|Kritik bölüm olmadığından hiçbir şey yapmaz.|

## <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection`[Ccomcriticalhandle bölümünde](../../atl/reference/ccomcriticalsection-class.md)bulunan yöntemleri yansıtır. Ancak `CComFakeCriticalSection` önemli bir bölüm sağlamaz; Bu nedenle, yöntemleri hiçbir şey yapmaz.

Genellikle, `CComFakeCriticalSection` **`typedef`** ya da bir adı ile kullanırsınız `AutoCriticalSection` `CriticalSection` . [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)kullanılırken, her ikisi de bu **`typedef`** ad başvurusudur `CComFakeCriticalSection` . [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)kullanılırken, sırasıyla [Ccomautocriticalhandle bölümüne](../../atl/reference/ccomautocriticalsection-class.md) ve öğesine başvurırlar `CComCriticalSection` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a> CComFakeCriticalSection:: Init

Kritik bölüm olmadığından hiçbir şey yapmaz.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a> CComFakeCriticalSection:: Lock

Kritik bölüm olmadığından hiçbir şey yapmaz.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a> CComFakeCriticalSection:: Term

Kritik bölüm olmadığından hiçbir şey yapmaz.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a> CComFakeCriticalSection:: unlock

Kritik bölüm olmadığından hiçbir şey yapmaz.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
