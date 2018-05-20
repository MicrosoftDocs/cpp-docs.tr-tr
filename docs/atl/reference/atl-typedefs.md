---
title: ATL tür tanımları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcore/ATL::_ATL_BASE_MODULE
- atlbase/ATL::_ATL_COM_MODULE
- atlbase/ATL::_ATL_MODULE
- atlbase/ATL::_ATL_WIN_MODULE
- atlutil/ATL::ATL_URL_PORT
- atlbase/ATL::CComDispatchDriver
- atlbase/ATL::CComGlobalsThreadModel
- atlbase/ATL::CComObjectThreadModel
- atlwin/ATL::CContainedWindow
- atlpath/ATL::CPath
- atlpath/ATL::CPathA
- atlpath/ATL::CPathW
- " atlsimpcoll/ATL::CSimpleValArray"
- " atlutil/ATL::LPCURL"
- atlbase/ATL::DefaultThreadTraits
- atlutil/ATL::LPURL
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 811dbda4360bcb3a618a4ceaa5228e57dab312ae
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="atl-typedefs"></a>ATL tür tanımları
Etkin Şablon Kütüphanesi aşağıdaki tür tanımları içerir.  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|Temel bir typedef olarak tanımlanan [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|  
|[_ATL_COM_MODULE](#_atl_com_module)|Temel bir typedef olarak tanımlanan [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|  
|[_ATL_MODULE](#_atl_module)|Temel bir typedef olarak tanımlanan [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|  
|[_ATL_WIN_MODULE](#_atl_win_module)|Temel bir typedef olarak tanımlanan [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|Tarafından kullanılan türü [CUrl](../../atl/reference/curl-class.md) bir bağlantı noktası numarası belirtmek için.|  
|[CComDispatchDriver](#ccomdispatchdriver)|Bu sınıf COM arabirim işaretçileri yönetir.|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Uygun iş parçacığı kullanılan iş parçacığı modelini bakılmaksızın modeli yöntemleri çağırır.|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Uygun iş parçacığı kullanılan iş parçacığı modelini bakılmaksızın modeli yöntemleri çağırır.|  
|[CContainedWindow](#ccontainedwindow)|Bu sınıf, bir alt uzmanlaşması **CContainedWindowT.**|  
|[CPath](#cpath)|Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CString`.|  
|[CPathA](#cpatha)|Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CStringA`.|  
|[CPathW](#cpathw)|Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CStringW`.|  
|[CSimpleValArray](#csimplevalarray)|Basit türler depolamak için bir dizi temsil eder.|  
|[DefaultThreadTraits](#defaultthreadtraits)|Varsayılan iş parçacığı nitelikler sınıfı.|  
|[LPCURL](#lpcurl)|Bir işaretçi bir sabite [CUrl](../../atl/reference/curl-class.md) nesnesi.|  
|[LPURL](#lpurl)|Bir işaretçi bir [CUrl](../../atl/reference/curl-class.md) nesnesi.|  
  
##  <a name="_atl_base_module"></a>  _ATL_BASE_MODULE  
 Üzerinde _ATL_BASE_MODULE70 dayalı bir typedef olarak tanımlanır.  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her ATL projede kullanılır. Temel [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).  
  
 ATL 7.0 modül sınıfları parçası olan sınıflar _ATL_BASE_MODULE yapısından türetilir.  ATL modül sınıfları hakkında daha fazla bilgi için başvurmak [COM modülleri sınıfları](../../atl/com-modules-classes.md).  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlcore.h

##  <a name="_atl_com_module"></a>  _ATL_COM_MODULE  
 Üzerinde _ATL_COM_MODULE70 dayalı bir typedef olarak tanımlanır.  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>Açıklamalar  
 COM özellikleri kullanan ATL projeleri tarafından kullanılır. Temel [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlbase.h
  
##  <a name="_atl_module"></a>  _ATL_MODULE  
 Üzerinde _ATL_MODULE70 dayalı bir typedef olarak tanımlanır.  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
## <a name="requirements"></a>Gereksinimler
**Başlık:** 
  
### <a name="remarks"></a>Açıklamalar  
 Temel [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).  
  
##  <a name="_atl_win_module"></a>  _ATL_WIN_MODULE  
 Üzerinde _ATL_WIN_MODULE70 dayalı bir typedef olarak tanımlanır.  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Pencereleme özellikleri kullanan ATL projeleri tarafından kullanılır. Temel [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlbase.h 
  
##  <a name="atl_url_port"></a>  ATL_URL_PORT 
  Tarafından kullanılan türü [CUrl](curl-class.md) bir bağlantı noktası numarası belirtmek için.
```  
typedef WORD ATL_URL_PORT;
```  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlutil.h

##  <a name="ccomdispatchdriver"></a>  CComDispatchDriver  
 Bu sınıf COM arabirim işaretçileri yönetir.  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
## <a name="requirements"></a>Gereksinimler
**Başlık:** atlbase.h
  
##  <a name="ccomglobalsthreadmodel"></a>  CComGlobalsThreadModel  
 Uygun iş parçacığı kullanılan iş parçacığı modelini bakılmaksızın modeli yöntemleri çağırır.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanız tarafından kullanılan iş parçacığı modeline bağlı olarak `typedef` adı `CComGlobalsThreadModel` ya da başvurduğu [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Bu sınıfların ek sağlamak `typedef` kritik bölümü sınıf başvurmak için adları.  
  
> [!NOTE]
> `CComGlobalsThreadModel` sınıf başvurmuyor [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 Kullanarak `CComGlobalsThreadModel` belirli bir iş parçacığı modeli sınıf belirtme boşaltır. Kullanılan iş parçacığı modelini bağımsız olarak, uygun yöntemleri çağrılır.  
  
 Ek olarak `CComGlobalsThreadModel`, ATL sağlar `typedef` adı [CComObjectThreadModel](#ccomobjectthreadmodel). Her tarafından başvurulan sınıfı `typedef` iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:  
  
|typedef|Çoklu iş parçacığı oluşturma|Apartman iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M = `CComMultiThreadModel`  
  
 Kullanım `CComObjectThreadModel` tek nesne sınıfı içinde. Kullanım `CComGlobalsThreadModel` nesnede programınıza genel olarak kullanılabilir veya birden çok iş parçacıkları arasında modülü kaynakları korumak istediğinizde.  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlbase.h
  
##  <a name="ccomobjectthreadmodel"></a>  CComObjectThreadModel  
 Uygun iş parçacığı kullanılan iş parçacığı modelini bakılmaksızın modeli yöntemleri çağırır.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComObjectThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanız tarafından kullanılan iş parçacığı modeline bağlı olarak `typedef` adı `CComObjectThreadModel` ya da başvurduğu [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Bu sınıfların ek sağlamak `typedef` kritik bölümü sınıf başvurmak için adları.  
  
> [!NOTE]
> `CComObjectThreadModel` sınıf başvurmuyor [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 Kullanarak `CComObjectThreadModel` belirli bir iş parçacığı modeli sınıf belirtme boşaltır. Kullanılan iş parçacığı modelini bağımsız olarak, uygun yöntemleri çağrılır.  
  
 Ek olarak `CComObjectThreadModel`, ATL sağlar `typedef` adı [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Her tarafından başvurulan sınıfı `typedef` iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:  
  
|typedef|Çoklu iş parçacığı oluşturma|Apartman iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M = `CComMultiThreadModel`  
  
 Kullanım `CComObjectThreadModel` tek nesne sınıfı içinde. Kullanım `CComGlobalsThreadModel` ya da bir nesne içinde programınızı veya birden çok iş parçacıkları arasında modülü kaynakları korumak istediğinizde genel olarak kullanılabilir.  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlbase.h
  
##  <a name="ccontainedwindow"></a>  CContainedWindow  
 Bu sınıf, bir alt uzmanlaşması **CContainedWindowT.**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlwin.h
  
### <a name="remarks"></a>Açıklamalar  
 `CContainedWindow` bir alt uzmanlaşması olan [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md). Taban sınıfı veya özellikleri değiştirmek istiyorsanız, kullanmak `CContainedWindowT` doğrudan.  
  
##  <a name="cpath"></a>  CPath  
 Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CString`.  
  
```   
typedef CPathT<CString> CPath;   
```  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlpath.h
  
##  <a name="cpatha"></a>  CPathA  
 Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CStringA`.  
  
```   
typedef CPathT<CStringA> CPathA;   
```

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlpath.h  
  
##  <a name="cpathw"></a>  CPathW  
 Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CStringW`.  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
## <a name="requirements"></a>Gereksinimler
**Başlık:** atlpath.h
  
##  <a name="csimplevalarray"></a>  CSimpleValArray  
 Basit türler depolamak için bir dizi temsil eder.  
  
```   
#define CSimpleValArray CSimpleArray   
```  

  
### <a name="remarks"></a>Açıklamalar  
 `CSimpleValArray` oluşturma ve yönetme basit veri türleri içeren diziler için sağlanır. Basit bir olan #, define [CSimpleArray](../../atl/reference/csimplearray-class.md).  


## <a name="requirements"></a>Gereksinimler
**Başlık:** atlsimpcoll.h
  
##  <a name="lpcurl"></a>  LPCURL  
 Bir işaretçi bir sabite [CUrl](../../atl/reference/curl-class.md) nesnesi.  
  
```   
typedef const CUrl* LPCURL;   
```  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlutil.h

##  <a name="defaultthreadtraits"></a>  DefaultThreadTraits
Varsayılan iş parçacığı nitelikler sınıfı.

### <a name="syntax"></a>Sözdizimi
```  
      #if defined(_MT)  
   typedef CRTThreadTraits DefaultThreadTraits;  
#else  
   typedef Win32ThreadTraits DefaultThreadTraits;  
#endif  
```

## <a name="remarks"></a>Açıklamalar
Geçerli projenin birden çok iş parçacıklı CRT kullanıyorsa, DefaultThreadTraits CRTThreadTraits tanımlanır. Aksi halde, Win32ThreadTraits kullanılır.


## <a name="requirements"></a>Gereksinimler
**Başlık:** atlbase.h
  
##  <a name="lpurl"></a>  LPURL  
 Bir işaretçi bir [CUrl](../../atl/reference/curl-class.md) nesnesi.  
  
```   
typedef CUrl* LPURL;   
```  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlutil.h


## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md)   
 [İşlevler](../../atl/reference/atl-functions.md)   
 [Genel değişkenler](../../atl/reference/atl-global-variables.md)   
 [Sınıflar ve yapılar](../../atl/reference/atl-classes.md) [makroları](../../atl/reference/atl-macros.md)   
