---
title: Ithreadpoolconfig arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 935175f522dd0b41851763f7b76781228c1881c0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880160"
---
# <a name="ithreadpoolconfig-interface"></a>Ithreadpoolconfig arabirimi
Bu arabirim, iş parçacığı havuzu yapılandırmak için yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetSize](#getsize)|Havuzda iş parçacığı sayısını almak için bu yöntemi çağırın.|  
|[GetTimeout](#gettimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.|  
|[SetSize](#setsize)|Havuzda iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.|  
|[SetTimeout](#settimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim tarafından uygulanan [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="getsize"></a>  IThreadPoolConfig::GetSize  
 Havuzda iş parçacığı sayısını almak için bu yöntemi çağırın.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Parametreler  
 *pnNumThreads*  
 [out] Değişkeninin adresi, başarı, havuzda iş parçacığı sayısını alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Parametreler  
 *pdwMaxWait*  
 [out] Başarı durumunda, iş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi alır. değişkenin adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="example"></a>Örnek  
 Bkz: [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="setsize"></a>  IThreadPoolConfig::SetSize  
 Havuzda iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Parametreler  
 *nNumThreads*  
 İstenen havuzundaki iş parçacığı sayısı.  
  
 Varsa *nNumThreads* olan negatif mutlak değerini toplam iş parçacığı sayısını almak için makinede işlemci sayısını çarpılacağı.  
  
 Varsa *nNumThreads* sıfır [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) toplam iş parçacığı sayısını almak için makinede işlemci sayısını çarpılacağı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="example"></a>Örnek  
 Bkz: [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwMaxWait*  
 İstenen en uzun süreyi milisaniye kapatmak bir iş parçacığı için iş parçacığı havuzu bekler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="example"></a>Örnek  
 Bkz: [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../atl/reference/atl-classes.md)   
 [CThreadPool Sınıfı](../../atl/reference/cthreadpool-class.md)
