---
title: CComCriticalSection Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
ms.openlocfilehash: f3991d217fbc201bd428ed2522a5c4c25e074928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327963"
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection Sınıfı

Bu sınıf, kritik bir bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[kcomcriticalsection::ccomcriticalsection](#ccomcriticalsection)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComCriticalSection::Init](#init)|Kritik bir bölüm nesnesi oluşturur ve başharfe bleştirir.|
|[Ccomcriticalsection::kilit](#lock)|Kritik bölüm nesnesinin sahipliğini alır.|
|[kcomcriticalsection:terim](#term)|Kritik bölüm nesnesi tarafından kullanılan sistem kaynaklarını serbest bırakır.|
|[Ccomcriticalsection::Unlock](#unlock)|Kritik bölüm nesnesinin sahipliğini salar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CcomCriticalSection::m_sec](#m_sec)|CRITICAL_SECTION bir nesne.|

## <a name="remarks"></a>Açıklamalar

`CComCriticalSection`sınıf [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)benzer , açıkça başlatmave kritik bölümü serbest bırakmak dışında.

Genellikle, `CComCriticalSection` **typedef** adı [CriticalSection](ccommultithreadmodel-class.md#criticalsection)ile kullanın. `CComCriticalSection` [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılırken bu ad başvurur.

Bu sınıfı aramaktan daha güvenli bir şekilde ve `Unlock` doğrudan `Lock` kullanmak için [CComCritSecLock Sınıfı'na](../../atl/reference/ccomcritseclock-class.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="ccomcriticalsectionccomcriticalsection"></a><a name="ccomcriticalsection"></a>kcomcriticalsection::ccomcriticalsection

Oluşturucu.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

[m_sec](#m_sec) veri üyesini NULL olarak ayarlar.

## <a name="ccomcriticalsectioninit"></a><a name="init"></a>CComCriticalSection::Init

[Win32](#m_sec) işlevini [çağırır InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection), m_sec veri üyesi bulunan kritik bölüm nesnesi başharflerini.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı, E_OUTOFMEMORY veya başarısızlık E_FAIL S_OK verir.

## <a name="ccomcriticalsectionlock"></a><a name="lock"></a>Ccomcriticalsection::kilit

Iş parçacığı [m_sec](#m_sec) veri üyesi bulunan kritik bölüm nesnesinin sahipliğini alabilir kadar bekler Win32 işlevi [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)çağırır.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı, E_OUTOFMEMORY veya başarısızlık E_FAIL S_OK verir.

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesi önce [Init](#init) yöntemine bir çağrı ile baş harfe getirilmelidir. Korumalı kod yürütmetamamlandığında, iş parçacığı kritik bölümün sahipliğini serbest bırakmak için [Unlock'u](#unlock) aramalıdır.

## <a name="ccomcriticalsectionm_sec"></a><a name="m_sec"></a>CcomCriticalSection::m_sec

Tüm `CComCriticalSection` yöntemler tarafından kullanılan kritik bir bölüm nesnesi içerir.

```
CRITICAL_SECTION m_sec;
```

## <a name="ccomcriticalsectionterm"></a><a name="term"></a>kcomcriticalsection:terim

[Win32](#m_sec) işlevini, m_sec veri üyesinde bulunan kritik bölüm nesnesi tarafından kullanılan tüm kaynakları serbest bırakan [DeleteCriticalSection'ı](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)çağırır.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan sonra, `Term` kritik bölüm artık eşitleme için kullanılamaz.

## <a name="ccomcriticalsectionunlock"></a><a name="unlock"></a>Ccomcriticalsection::Unlock

[win32](#m_sec) işlevini çağıran [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection), m_sec veri üyesi bulunan kritik bölüm nesnesinin sahipliğini bültenleri.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Önce sahipliği elde etmek için iş parçacığının [Kilit](#lock) yöntemini araması gerekir. Her çağrı, `Lock` kritik bölümün `Unlock` sahipliğini serbest bırakmak için karşılık gelen bir çağrı gerektirir.

## <a name="see-also"></a>Ayrıca bkz.

[CComFakeCriticalSection Sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CComCritSecLock Sınıfı](../../atl/reference/ccomcritseclock-class.md)
