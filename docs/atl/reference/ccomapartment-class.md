---
title: CComApartment Sınıfı
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
ms.openlocfilehash: 13141d27592f6f40ea7b0529c61baba2fe83a10a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321114"
---
# <a name="ccomapartment-class"></a>CComApartment Sınıfı

Bu sınıf, iş parçacığı havuzlu EXE modülünde bir daireyi yönetmek için destek sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComApartment
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Ccomapartment::ccomapartment](#ccomapartment)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomApartment::Daire](#apartment)|İş parçacığının başlangıç adresini işaretler.|
|[CcomApartment::getlocksayısı](#getlockcount)|İş parçacığının geçerli kilit sayısını döndürür.|
|[CcomApartment::Kilit](#lock)|İş parçacığının kilit sayısını damlar.|
|[CcomApartment::Kilidini Aç](#unlock)|İş parçacığının kilit sayısını eriter.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|İş parçacığının tanımlayıcısını içerir.|
|[CComApartment::m_hThread](#m_hthread)|İş parçacığının tutamacını içerir.|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|İş parçacığının geçerli kilit sayısını içerir.|

## <a name="remarks"></a>Açıklamalar

`CComApartment`[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) tarafından iplik havuzlu EXE modülündeki bir daireyi yönetmek için kullanılır. `CComApartment`bir iş parçacığı üzerinde kilit sayısını artım ve decrementing için yöntemler sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomapartmentapartment"></a><a name="apartment"></a>CcomApartment::Daire

İş parçacığının başlangıç adresini işaretler.

```
DWORD Apartment();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0.

### <a name="remarks"></a>Açıklamalar

CComAutoThreadModule sırasında otomatik olarak [ayarlanır::Init](../../atl/reference/ccomautothreadmodule-class.md#init).

## <a name="ccomapartmentccomapartment"></a><a name="ccomapartment"></a>Ccomapartment::ccomapartment

Oluşturucu.

```
CComApartment();
```

### <a name="remarks"></a>Açıklamalar

`CComApartment` veri üyelerini [m_nLockCnt](#m_nlockcnt) ve [m_hThread.](#m_hthread)

## <a name="ccomapartmentgetlockcount"></a><a name="getlockcount"></a>CcomApartment::getlocksayısı

İş parçacığının geçerli kilit sayısını döndürür.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığının kilit sayısı.

## <a name="ccomapartmentlock"></a><a name="lock"></a>CcomApartment::Kilit

İş parçacığının kilit sayısını damlar.

```
LONG Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

[CComAutoThreadModule tarafından çağrılan::Kilit](../../atl/reference/ccomautothreadmodule-class.md#lock).

İş parçacığı üzerindeki kilit sayısı istatistiksel amaçlar için kullanılır.

## <a name="ccomapartmentm_dwthreadid"></a><a name="m_dwthreadid"></a>CComApartment::m_dwThreadID

İş parçacığının tanımlayıcısını içerir.

```
DWORD m_dwThreadID;
```

## <a name="ccomapartmentm_hthread"></a><a name="m_hthread"></a>CComApartment::m_hThread

İş parçacığının tutamacını içerir.

```
HANDLE m_hThread;
```

## <a name="ccomapartmentm_nlockcnt"></a><a name="m_nlockcnt"></a>CComApartment::m_nLockCnt

İş parçacığının geçerli kilit sayısını içerir.

```
LONG m_nLockCnt;
```

## <a name="ccomapartmentunlock"></a><a name="unlock"></a>CcomApartment::Kilidini Aç

İş parçacığının kilit sayısını eriter.

```
LONG Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

[CComAutoThreadModule tarafından çağrılan::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).

İş parçacığı üzerindeki kilit sayısı istatistiksel amaçlar için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
