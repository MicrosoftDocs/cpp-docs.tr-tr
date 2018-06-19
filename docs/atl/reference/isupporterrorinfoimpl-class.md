---
title: ISupportErrorInfoImpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 3e226f66d6ddd20181f083f723568acb1cc647c7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364587"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl sınıfı
Bu sınıf, bir varsayılan uygulamasını sağlar [ISupportErrorInfo arabirimi](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) ve tek bir arabirim bir nesne üzerinde hataları oluşturduğunda kullanılabilir.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>Parametreler  
 `piid`  
 Bir işaretçi destekleyen bir arabirim IID [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Arabirim tarafından tanımlanan olup olmadığını gösteren `riid` destekleyen [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) arabirimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 [ISupportErrorInfo arabirimi](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) hata bilgilerini istemciye döndürdüğünü sağlar. Nesneleri kullanan **IErrorInfo** uygulamalıdır **ISupportErrorInfo**.  
  
 Sınıf `ISupportErrorInfoImpl` bir varsayılan uygulamayı sağlar **ISupportErrorInfo** ve tek bir arabirim bir nesne üzerinde hataları oluşturduğunda kullanılabilir. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 Arabirim tarafından tanımlanan olup olmadığını gösteren `riid` destekleyen [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) arabirimi.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ISupportErrorInfo::InterfaceSupportsErrorInfo](http://msdn.microsoft.com/en-us/a54ef18d-ee3f-4483-ac4a-99d758f0960a) Windows SDK.  
  
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
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
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
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
