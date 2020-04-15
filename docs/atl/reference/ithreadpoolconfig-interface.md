---
title: IThreadPoolConfig Arabirimi
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
ms.openlocfilehash: e4b90534fa89ef2aeffe4cd682d92efc16452487
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326351"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig Arabirimi

Bu arabirim, iş parçacığı havuzuyapılandırma yöntemleri sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[GetSize](#getsize)|Havuzdaki iş parçacığı sayısını almak için bu yöntemi arayın.|
|[GetTimeout](#gettimeout)|İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniyecinsinden en fazla zamanı almak için bu yöntemi arayın.|
|[SetSize](#setsize)|Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi arayın.|
|[Settimeout](#settimeout)|İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden maksimum süreyi ayarlamak için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Bu arayüz [CThreadPool](../../atl/reference/cthreadpool-class.md)tarafından uygulanmaktadır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a>IThreadPoolConfig::GetSize

Havuzdaki iş parçacığı sayısını almak için bu yöntemi arayın.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>Parametreler

*pnNumThreads*<br/>
[çıkış] Başarı üzerine, havuzdaki iş parçacığı sayısını alan değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a>IThreadPoolConfig::GetTimeout

İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniyecinsinden en fazla zamanı almak için bu yöntemi arayın.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>Parametreler

*pdwMaxWait*<br/>
[çıkış] Başarı da, iş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden en fazla süreyi alan değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

Bkz. [IThreadPoolConfig::GetSize](#getsize).

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a>IThreadPoolConfig::SetSize

Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi arayın.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>Parametreler

*nNumThreads*<br/>
Havuzda istenen iş parçacığı sayısı.

*NNumThreads* negatif ise, mutlak değeri makinedeki işlemci sayısı ile çarpımır ve toplam iş parçacığı sayısını elde eder.

*nNumThreads* sıfır ise, ATLS_DEFAULT_THREADSPERPROC makinedeki işlemci sayısı ile çarpımır ve toplam iş parçacığı sayısını elde edecektir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

Bkz. [IThreadPoolConfig::GetSize](#getsize).

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a>IThreadPoolConfig::SetTimeout

İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden maksimum süreyi ayarlamak için bu yöntemi arayın.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>Parametreler

*dwMaxWait*<br/>
İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden istenen maksimum süre.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

Bkz. [IThreadPoolConfig::GetSize](#getsize).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[CThreadPool Sınıfı](../../atl/reference/cthreadpool-class.md)
