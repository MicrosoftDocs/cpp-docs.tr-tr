---
title: CComCritSecLock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab3c4b349b64b96b8aeb7a53d6bf8809f41cea7b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097789"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[CComAutoCriticalSection Sınıfı](../../atl/reference/ccomautocriticalsection-class.md)
