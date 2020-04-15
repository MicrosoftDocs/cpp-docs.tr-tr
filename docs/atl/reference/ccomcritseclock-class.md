---
title: CComCritSecLock Sınıfı
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
ms.openlocfilehash: 24d141c5b0ec703feadcd7db96da33f9de940dda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327958"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock Sınıfı

Bu sınıf, kritik bir bölüm nesnesini kilitleme ve açma yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Parametreler

*TLock*<br/>
Kilitlenecek ve kilitlenecek nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|Oluşturucu.|
|[CComCritSecLock::~CComCritSecLock](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComCritSecLock::Kilit](#lock)|Kritik bölüm nesnesini kilitlemek için bu yöntemi çağırın.|
|[CComCritSecLock::Kilidini aç](#unlock)|Kritik bölüm nesnesinin kilidini açmak için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

[CComCriticalSection Class veya CComAutoCriticalSection](../../atl/reference/ccomcriticalsection-class.md) [Class](../../atl/reference/ccomautocriticalsection-class.md)ile daha güvenli bir şekilde nesneleri kilitlemek ve kilidini açmak için bu sınıfı kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a>CComCritSecLock::CComCritSecLock

Oluşturucu.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Parametreler

*Cs*<br/>
Kritik bölüm nesnesi.

*bInitialLock*<br/>
İlk kilit durumu: **gerçek** kilitli anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesini başharfe ait hale.

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a>CComCritSecLock::~CComCritSecLock

Yıkıcı.

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesinin kilidini açar.

## <a name="ccomcritseclocklock"></a><a name="lock"></a>CComCritSecLock::Kilit

Kritik bölüm nesnesini kilitlemek için bu yöntemi çağırın.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla kilitlenmişse veya hata yla ilgili bir Hata HRESULT'ı S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne zaten kilitliyse, hata ayıklama yapılarda bir Assert hatası oluşur.

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a>CComCritSecLock::Kilidini aç

Kritik bölüm nesnesinin kilidini açmak için bu yöntemi arayın.

```
void Unlock() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnenin kilidi zaten açıksa, hata ayıklama yapılarında bir Assert hatası oluşur.

## <a name="see-also"></a>Ayrıca bkz.

[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[CComAutoCriticalSection Sınıfı](../../atl/reference/ccomautocriticalsection-class.md)
