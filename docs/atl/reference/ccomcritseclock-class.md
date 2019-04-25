---
title: CComCritSecLock sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
ms.openlocfilehash: 045e64504707fa8978c8236b376037d9f57bf12c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259813"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock sınıfı

Bu sınıf, kilitleme ve kritik bölüm nesne kilidi kaldırma için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Parametreler

*TLock*<br/>
Kilitli ve kilidi nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|Oluşturucu.|
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCritSecLock::Lock](#lock)|Kritik bölüm nesneyi kilitlemek için bu yöntemi çağırın.|
|[CComCritSecLock::Unlock](#unlock)|Kritik bölüm nesne kilidini açmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Kilitlemek ve nesneleri ile daha güvenli bir şekilde kilidini açmak için bu sınıfı kullanan [CComCriticalSection sınıfı](../../atl/reference/ccomcriticalsection-class.md) veya [CComAutoCriticalSection sınıfı](../../atl/reference/ccomautocriticalsection-class.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock

Oluşturucu.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Parametreler

*cs*<br/>
Kritik bölüm nesne.

*bInitialLock*<br/>
İlk kilitleme durumu: **true** kilitli anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesini başlatır.

##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock

Yıkıcı.

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesne kilidini açar.

##  <a name="lock"></a>  CComCritSecLock::Lock

Kritik bölüm nesneyi kilitlemek için bu yöntemi çağırın.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla kilitlenmişse S_OK veya bir hata HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne zaten kilitli, bir onay hata hata ayıklama yapılarında meydana gelir.

##  <a name="unlock"></a>  CComCritSecLock::Unlock

Kritik bölüm nesne kilidini açmak için bu yöntemi çağırın.

```
void Unlock() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne kilidi zaten açılmış, bir onay hata hata ayıklama yapılarında meydana gelir.

## <a name="see-also"></a>Ayrıca bkz.

[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[CComAutoCriticalSection Sınıfı](../../atl/reference/ccomautocriticalsection-class.md)
