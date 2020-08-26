---
title: IThreadPoolConfig arabirimi
ms.date: 11/04/2016
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
ms.openlocfilehash: cba82055c292fc966dc2328773cce4aa64d45a64
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835434"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig arabirimi

Bu arabirim, bir iş parçacığı havuzu yapılandırmak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[GetSize](#getsize)|Havuzdaki iş parçacığı sayısını almak için bu yöntemi çağırın.|
|[GetTimeout](#gettimeout)|İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye olarak almak için bu yöntemi çağırın.|
|[Çalışma](#setsize)|Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.|
|[SetTimeout](#settimeout)|İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye cinsinden ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, [CThreadPool](../../atl/reference/cthreadpool-class.md)tarafından uygulanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a> IThreadPoolConfig:: GetSize

Havuzdaki iş parçacığı sayısını almak için bu yöntemi çağırın.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>Parametreler

*pnNumThreads*<br/>
dışı Başarılı olan değişkenin, havuzdaki iş parçacığı sayısını aldığı değişken adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a> IThreadPoolConfig:: GetTimeout

İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye olarak almak için bu yöntemi çağırın.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>Parametreler

*pdwMaxWait*<br/>
dışı Başarılı olan değişkenin, iş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye olarak alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

Bkz. [IThreadPoolConfig:: GetSize](#getsize).

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a> IThreadPoolConfig:: SetSize

Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>Parametreler

*nNumThreads*<br/>
Havuzdaki istenen iş parçacığı sayısı.

*NNumThreads* negatifse, toplam iş parçacığı sayısını almak için, mutlak değeri makinedeki işlemci sayısıyla çarpılacak.

*NNumThreads* sıfırsa, ATLS_DEFAULT_THREADSPERPROC toplam iş parçacığı sayısını almak için makinedeki işlemci sayısıyla çarpılacak.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

Bkz. [IThreadPoolConfig:: GetSize](#getsize).

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a> IThreadPoolConfig:: SetTimeout

İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye cinsinden ayarlamak için bu yöntemi çağırın.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>Parametreler

*dwMaxWait*<br/>
İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleneceği milisaniye cinsinden istenen en uzun süre.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

Bkz. [IThreadPoolConfig:: GetSize](#getsize).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[CThreadPool sınıfı](../../atl/reference/cthreadpool-class.md)
