---
title: CComApartment sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
dev_langs:
- C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39750bcb6b8852e692e52f163e83bb815ecebe97
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755443"
---
# <a name="ccomapartment-class"></a>CComApartment sınıfı

Bu sınıf, bir iş parçacığı havuza EXE modülündeki bir daire yönetmek için destek sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComApartment
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComApartment::Apartment](#apartment)|İş parçacığının başlangıç adresi işaretler.|
|[CComApartment::GetLockCount](#getlockcount)|İş parçacığının geçerli kilit sayacını döndürür.|
|[CComApartment::Lock](#lock)|İş parçacığının kilit sayacını artırır.|
|[CComApartment::Unlock](#unlock)|İş parçacığının kilit sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|İş parçacığının tanımlayıcısını içerir.|
|[CComApartment::m_hThread](#m_hthread)|İş parçacıkları işlemesini içerir.|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|İş parçacığının geçerli kilit sayacını içerir.|

## <a name="remarks"></a>Açıklamalar

`CComApartment` tarafından kullanılan [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) bir iş parçacığı havuza EXE modülü bir grupta yönetmek için. `CComApartment` bir iş parçacığında yöntemleri artırma ve azaltma kilit sayısı sağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="apartment"></a>  CComApartment::Apartment

İş parçacığının başlangıç adresi işaretler.

```
DWORD Apartment();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0.

### <a name="remarks"></a>Açıklamalar

Sırasında otomatik olarak [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).

##  <a name="ccomapartment"></a>  CComApartment::CComApartment

Oluşturucu.

```
CComApartment();
```

### <a name="remarks"></a>Açıklamalar

Başlatır `CComApartment` veri üyeleri [m_nLockCnt](#m_nlockcnt) ve [m_hThread](#m_hthread).

##  <a name="getlockcount"></a>  CComApartment::GetLockCount

İş parçacığının geçerli kilit sayacını döndürür.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı üzerinde kilit sayısı.

##  <a name="lock"></a>  CComApartment::Lock

İş parçacığının kilit sayacını artırır.

```
LONG Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

### <a name="remarks"></a>Açıklamalar

Çağıran [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).

İş parçacığı üzerinde kilit sayacını İstatistiksel amaçlar için kullanılır.

##  <a name="m_dwthreadid"></a>  CComApartment::m_dwThreadID

İş parçacığının tanımlayıcısını içerir.

```
DWORD m_dwThreadID;
```

##  <a name="m_hthread"></a>  CComApartment::m_hThread

İş parçacıkları işlemesini içerir.

```
HANDLE m_hThread;
```

##  <a name="m_nlockcnt"></a>  CComApartment::m_nLockCnt

İş parçacığının geçerli kilit sayacını içerir.

```
LONG m_nLockCnt;
```

##  <a name="unlock"></a>  CComApartment::Unlock

İş parçacığının kilit sayısını azaltır.

```
LONG Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

### <a name="remarks"></a>Açıklamalar

Çağıran [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).

İş parçacığı üzerinde kilit sayacını İstatistiksel amaçlar için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
