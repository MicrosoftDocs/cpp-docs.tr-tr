---
title: IThreadPoolConfig arabirimi | Microsoft Docs
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
ms.openlocfilehash: 237671ce971d54209f3889fd93396fb4e0a42fee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363735"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig arabirimi
Bu arabirim, bir iş parçacığı havuzu yapılandırmak için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetSize](#getsize)|İş parçacığı sayısını havuzda almak için bu yöntemi çağırın.|  
|[GetTimeout](#gettimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.|  
|[SetSize](#setsize)|Havuzundaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.|  
|[SetTimeout](#settimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim tarafından uygulanan [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="getsize"></a>  IThreadPoolConfig::GetSize  
 İş parçacığı sayısını havuzda almak için bu yöntemi çağırın.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Parametreler  
 `pnNumThreads`  
 [out] Adresi değişkenin, başarı, havuzda iş parçacığı sayısını alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Parametreler  
 `pdwMaxWait`  
 [out] Adresi değişkenin, başarı, iş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="example"></a>Örnek  
 Bkz: [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="setsize"></a>  IThreadPoolConfig::SetSize  
 Havuzundaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Parametreler  
 `nNumThreads`  
 İş parçacığı havuzundaki istenen sayısı.  
  
 Varsa `nNumThreads` olan negatif mutlak değerini toplam iş parçacığı sayısını almak üzere makine işlemci sayısı çarpılacağı.  
  
 Varsa `nNumThreads` sıfır [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) toplam iş parçacığı sayısını almak üzere makine işlemci sayısı çarpılacağı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="example"></a>Örnek  
 Bkz: [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwMaxWait`  
 İstenen en uzun süre kapatmak bir iş parçacığı için iş parçacığı havuzu bekleyeceği milisaniye cinsinden.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="example"></a>Örnek  
 Bkz: [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../atl/reference/atl-classes.md)   
 [CThreadPool Sınıfı](../../atl/reference/cthreadpool-class.md)
