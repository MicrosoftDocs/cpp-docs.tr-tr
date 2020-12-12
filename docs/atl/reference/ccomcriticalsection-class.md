---
description: 'Daha fazla bilgi edinin: Ccomkritiksection sınıfı'
title: Ccomcriticalhandle bölüm sınıfı
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
ms.openlocfilehash: 7a6a3efef68a14cbda513ee60ed3980293514ad6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146737"
---
# <a name="ccomcriticalsection-class"></a>Ccomcriticalhandle bölüm sınıfı

Bu sınıf, kritik bir bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Ccomcriticalhandle Section:: Ccomcriticalhandle bölümü](#ccomcriticalsection)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccomcriticalhandle bölümü:: Init](#init)|Kritik bir bölüm nesnesi oluşturur ve başlatır.|
|[Ccomcriticalhandle Section:: Lock](#lock)|Kritik bölüm nesnesinin sahipliğini edinir.|
|[Ccomcriticalhandle Section:: Term](#term)|Kritik bölüm nesnesi tarafından kullanılan sistem kaynaklarını serbest bırakır.|
|[Ccomcriticalhandle bölümü:: unlock](#unlock)|Kritik bölüm nesnesinin sahipliğini yayınlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Ccomcriticalhandle bölümü:: m_sec](#m_sec)|CRITICAL_SECTION nesnesi.|

## <a name="remarks"></a>Açıklamalar

`CComCriticalSection` , [Ccomautocriticalhandle bölümüne](../../atl/reference/ccomautocriticalsection-class.md)benzerdir, ancak kritik bölümü açıkça başlatıp serbest bırakmanız gerekir.

Genellikle, `CComCriticalSection` **`typedef`** ad [CriticalHandle bölümünde](ccommultithreadmodel-class.md#criticalsection)kullanırsınız. Bu ad `CComCriticalSection` , [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılırken başvuruda bulunur.

Bu sınıfı çağırmadan daha güvenli bir yol için bkz. [CComCritSecLock sınıfı](../../atl/reference/ccomcritseclock-class.md) `Lock` `Unlock` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="ccomcriticalsectionccomcriticalsection"></a><a name="ccomcriticalsection"></a> Ccomcriticalhandle Section:: Ccomcriticalhandle bölümü

Oluşturucu.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

[M_sec](#m_sec) VERI üyesini null olarak ayarlar.

## <a name="ccomcriticalsectioninit"></a><a name="init"></a> Ccomcriticalhandle bölümü:: Init

[M_sec](#m_sec) veri üyesinde bulunan kritik bölüm nesnesini başlatan [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)Win32 işlevini çağırır.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, E_OUTOFMEMORY veya E_FAIL hatada S_OK döndürür.

## <a name="ccomcriticalsectionlock"></a><a name="lock"></a> Ccomcriticalhandle Section:: Lock

, İş parçacığının [m_sec](#m_sec) veri üyesinde bulunan kritik bölüm nesnesinin sahipliğini alıp alamamasını bekleyen Win32 Işlevi [entercriticalhandle bölümünü](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)çağırır.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, E_OUTOFMEMORY veya E_FAIL hatada S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesi önce [Init](#init) yöntemine yapılan bir çağrıyla başlatılmalıdır. Korunan kodun yürütülmesi tamamlandığında, kritik bölümün sahipliğini serbest bırakmak için iş parçacığının [kilit açma](#unlock) çağrısı gerekir.

## <a name="ccomcriticalsectionm_sec"></a><a name="m_sec"></a> Ccomcriticalhandle bölümü:: m_sec

Tüm yöntemler tarafından kullanılan kritik bir bölüm nesnesi içerir `CComCriticalSection` .

```
CRITICAL_SECTION m_sec;
```

## <a name="ccomcriticalsectionterm"></a><a name="term"></a> Ccomcriticalhandle Section:: Term

[M_sec](#m_sec) veri üyesinde bulunan kritik bölüm nesnesi tarafından kullanılan tüm kaynakları serbest bırakarak Win32 Işlevi [deletecriticalhandle bölümünü](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)çağırır.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bir kez `Term` çağrıldıktan sonra, kritik bölüm artık eşitleme için kullanılamaz.

## <a name="ccomcriticalsectionunlock"></a><a name="unlock"></a> Ccomcriticalhandle bölümü:: unlock

[M_sec](#m_sec) veri üyesinde bulunan kritik bölüm nesnesinin sahipliğini serbest bırakır [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)Win32 işlevini çağırır.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Sahipliği ilk olarak almak için, iş parçacığının [Lock](#lock) yöntemini çağırması gerekir. Her çağrısı `Lock` `Unlock` , kritik bölümün sahipliğini serbest bırakmak için öğesine karşılık gelen bir çağrı gerektirir.

## <a name="see-also"></a>Ayrıca bkz.

[CComFakeCriticalSection sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComCritSecLock sınıfı](../../atl/reference/ccomcritseclock-class.md)
