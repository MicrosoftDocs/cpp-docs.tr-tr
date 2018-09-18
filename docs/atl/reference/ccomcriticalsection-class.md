---
title: CComCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4678acbe251086f3a42e3544e155a191a5847f11
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101403"
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection sınıfı

Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCriticalSection::Init](#init)|Oluşturur ve kritik bölüm nesnesi başlatır.|
|[CComCriticalSection::Lock](#lock)|Kritik bölüm nesne sahipliğini alır.|
|[CComCriticalSection::Term](#term)|Kritik bölüm nesne tarafından kullanılan sistem kaynaklarını serbest bırakır.|
|[CComCriticalSection::Unlock](#unlock)|Kritik bölüm nesnenin sahipliğini serbest bırakır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|Bir CRITICAL_SECTION nesnesi.|

## <a name="remarks"></a>Açıklamalar

`CComCriticalSection` sınıfına benzer [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), siz açıkça başlatmak ve kritik bölüm yayın.

Genellikle, kullandığınız `CComCriticalSection` aracılığıyla **typedef** adı [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Bu ada başvuran `CComCriticalSection` olduğunda [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılıyor.  

Bkz: [CComCritSecLock sınıfı](../../atl/reference/ccomcritseclock-class.md) arama bu sınıf kullanmak daha güvenli bir şekilde `Lock` ve `Unlock` doğrudan.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection

Oluşturucu.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

Kümeleri [m_sec](#m_sec) veri üyesi null.

##  <a name="init"></a>  CComCriticalSection::Init

Win32 işlevini çağırır [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection), yer alan kritik bölüm nesnesi başlatır [m_sec](#m_sec) veri üyesi.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, E_OUTOFMEMORY veya hata durumunda E_FAIL başarılıysa S_OK döndürür.

##  <a name="lock"></a>  CComCriticalSection::Lock

Win32 işlevini çağırır [EnterCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-entercriticalsection), iş parçacığı kritik bölüm nesnenin içerdiği sahipliğini alabilir kadar hangi bekler [m_sec](#m_sec) veri üyesi.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, E_OUTOFMEMORY veya hata durumunda E_FAIL başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesi ilk çağrısı ile başlatılmalıdır [Init](#init) yöntemi. Korumalı kod yürütme sona erdiğinde, iş parçacığı çağırmalıdır [kilidini](#unlock) kritik bölüm sahipliğini serbest bırakmak için.

##  <a name="m_sec"></a>  CComCriticalSection::m_sec

Tüm tarafından kullanılan kritik bölüm nesnesi içeren `CComCriticalSection` yöntemleri.

```
CRITICAL_SECTION m_sec;
```

##  <a name="term"></a>  CComCriticalSection::Term

Win32 işlevini çağırır [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection), yer alan kritik bölüm nesnesi tarafından kullanılan tüm kaynakları serbest bırakır [m_sec](#m_sec) veri üyesi.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bir kez `Term` çağrılıp çağrılmadığını, kritik bölüm için eşitlemeyi artık kullanılabilir.

##  <a name="unlock"></a>  CComCriticalSection::Unlock

Win32 işlevini çağırır [LeaveCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-leavecriticalsection), yer alan kritik bölüm nesnenin sahipliğini serbest [m_sec](#m_sec) veri üyesi.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sahipliğini almak için iş parçacığı çağırmalıdır [kilit](#lock) yöntemi. Her çağrı `Lock` karşılık gelen bir çağrı gerektirir `Unlock` kritik bölüm sahipliğini serbest bırakmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[CComFakeCriticalSection Sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CComCritSecLock Sınıfı](../../atl/reference/ccomcritseclock-class.md)
