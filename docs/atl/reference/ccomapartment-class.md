---
description: 'Daha fazla bilgi edinin: CComApartment sınıfı'
title: CComApartment sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: de51d1eb04bfa0f0760ad741e19b237a9e72dc8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152327"
---
# <a name="ccomapartment-class"></a>CComApartment sınıfı

Bu sınıf, bir grubu iş parçacığı havuza alınmış bir EXE modülünde yönetmek için destek sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CComApartment
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComApartment:: CComApartment](#ccomapartment)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComApartment:: Apartment](#apartment)|İş parçacığının başlangıç adresini işaretler.|
|[CComApartment:: GetLockCount](#getlockcount)|İş parçacığının geçerli kilit sayısını döndürür.|
|[CComApartment:: Lock](#lock)|İş parçacığının kilit sayısını artırır.|
|[CComApartment:: unlock](#unlock)|İş parçacığının kilit sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComApartment:: m_dwThreadID](#m_dwthreadid)|İş parçacığının tanımlayıcısını içerir.|
|[CComApartment:: m_hThread](#m_hthread)|İş parçacığının işleyicisini içerir.|
|[CComApartment:: m_nLockCnt](#m_nlockcnt)|İş parçacığının geçerli kilit sayısını içerir.|

## <a name="remarks"></a>Açıklamalar

`CComApartment` , bir grubu iş parçacığı havuza alınmış bir EXE modülünde yönetmek için [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) tarafından kullanılır. `CComApartment` bir iş parçacığında kilit sayısını artırma ve azaltma için yöntemler sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomapartmentapartment"></a><a name="apartment"></a> CComApartment:: Apartment

İş parçacığının başlangıç adresini işaretler.

```
DWORD Apartment();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0.

### <a name="remarks"></a>Açıklamalar

[CComAutoThreadModule:: Init](../../atl/reference/ccomautothreadmodule-class.md#init)sırasında otomatik olarak ayarlanır.

## <a name="ccomapartmentccomapartment"></a><a name="ccomapartment"></a> CComApartment:: CComApartment

Oluşturucu.

```
CComApartment();
```

### <a name="remarks"></a>Açıklamalar

`CComApartment` [M_nLockCnt](#m_nlockcnt) ve [m_hThread](#m_hthread)veri üyelerini başlatır.

## <a name="ccomapartmentgetlockcount"></a><a name="getlockcount"></a> CComApartment:: GetLockCount

İş parçacığının geçerli kilit sayısını döndürür.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığında kilit sayısı.

## <a name="ccomapartmentlock"></a><a name="lock"></a> CComApartment:: Lock

İş parçacığının kilit sayısını artırır.

```
LONG Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

[CComAutoThreadModule:: Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)tarafından çağırılır.

İş parçacığında kilit sayısı istatistiksel amaçlar için kullanılır.

## <a name="ccomapartmentm_dwthreadid"></a><a name="m_dwthreadid"></a> CComApartment:: m_dwThreadID

İş parçacığının tanımlayıcısını içerir.

```
DWORD m_dwThreadID;
```

## <a name="ccomapartmentm_hthread"></a><a name="m_hthread"></a> CComApartment:: m_hThread

İş parçacığının işleyicisini içerir.

```
HANDLE m_hThread;
```

## <a name="ccomapartmentm_nlockcnt"></a><a name="m_nlockcnt"></a> CComApartment:: m_nLockCnt

İş parçacığının geçerli kilit sayısını içerir.

```
LONG m_nLockCnt;
```

## <a name="ccomapartmentunlock"></a><a name="unlock"></a> CComApartment:: unlock

İş parçacığının kilit sayısını azaltır.

```
LONG Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

[CComAutoThreadModule:: unlock](../../atl/reference/ccomautothreadmodule-class.md#lock)tarafından çağırılır.

İş parçacığında kilit sayısı istatistiksel amaçlar için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
