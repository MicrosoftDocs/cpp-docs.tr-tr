---
description: 'Daha fazla bilgi edinin: CComCritSecLock sınıfı'
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
ms.openlocfilehash: 7cad44f062fe75418da1f948c5f180283142779b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152106"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock sınıfı

Bu sınıf, kritik bir bölüm nesnesini kilitlemek ve kilidini açmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Parametreler

*TLock*<br/>
Kilitlenecek ve kilitlenmemiş nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCritSecLock:: CComCritSecLock](#ctor)|Oluşturucu.|
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCritSecLock:: Lock](#lock)|Kritik bölüm nesnesini kilitlemek için bu yöntemi çağırın.|
|[CComCritSecLock:: unlock](#unlock)|Kritik bölüm nesnesinin kilidini açmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Nesneleri [Ccomcriticalhandle bölüm sınıfı](../../atl/reference/ccomcriticalsection-class.md) veya [Ccomautocriticalhandle bölüm sınıfıyla](../../atl/reference/ccomautocriticalsection-class.md)daha güvenli bir şekilde kilitlemek ve kilitlerini açmak için bu sınıfı kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a> CComCritSecLock:: CComCritSecLock

Oluşturucu.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Kritik bölüm nesnesi.

*bInitialLock*<br/>
İlk kilit durumu: **`true`** kilitli anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesini başlatır.

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a> CComCritSecLock:: ~ CComCritSecLock

Yok edicisi.

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesinin kilidini açar.

## <a name="ccomcritseclocklock"></a><a name="lock"></a> CComCritSecLock:: Lock

Kritik bölüm nesnesini kilitlemek için bu yöntemi çağırın.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla kilitliyse S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne zaten kilitliyse hata ayıklama yapılarında bir onaylama hatası oluşur.

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a> CComCritSecLock:: unlock

Kritik bölüm nesnesinin kilidini açmak için bu yöntemi çağırın.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnenin kilidi zaten açıksa, hata ayıklama yapılarında bir onaylama hatası oluşur.

## <a name="see-also"></a>Ayrıca bkz.

[Ccomcriticalhandle bölüm sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Ccomautocriticalhandle bölüm sınıfı](../../atl/reference/ccomautocriticalsection-class.md)
