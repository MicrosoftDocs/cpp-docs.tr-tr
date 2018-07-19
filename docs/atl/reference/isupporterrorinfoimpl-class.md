---
title: Isupporterrorınfoımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 849107cc9f0d0611eb3dc9259fc317f73a961407
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026179"
---
# <a name="isupporterrorinfoimpl-class"></a>Isupporterrorınfoımpl sınıfı
Bu sınıfın bir varsayılan uygulamayı sağlar [ISupportErrorInfo arabirimi](http://msdn.microsoft.com/42d33066-36b4-4a5b-aa5d-46682e560f32) ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>Parametreler  
 *piid*  
 Laboratuvardaki destekleyen bir arabirim işaretçisi [IErrorInfo](http://msdn.microsoft.com/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Arabirim tarafından tanımlanan olup olmadığını gösteren `riid` destekler [IErrorInfo](http://msdn.microsoft.com/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) arabirimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 [ISupportErrorInfo arabirimi](http://msdn.microsoft.com/42d33066-36b4-4a5b-aa5d-46682e560f32) hata bilgilerini istemciye döndürdüğünü sağlar. Nesneleri kullanan `IErrorInfo` uygulamalıdır `ISupportErrorInfo`.  
  
 Sınıf `ISupportErrorInfoImpl` bir varsayılan uygulamayı sağlar `ISupportErrorInfo` ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 Arabirim tarafından tanımlanan olup olmadığını gösteren `riid` destekler [IErrorInfo](http://msdn.microsoft.com/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) arabirimi.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ISupportErrorInfo::InterfaceSupportsErrorInfo](http://msdn.microsoft.com/a54ef18d-ee3f-4483-ac4a-99d758f0960a) Windows SDK içinde.  
  
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
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
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
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
