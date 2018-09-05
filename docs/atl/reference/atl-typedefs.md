---
title: ATL Typedefs | Microsoft Docs
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
ms.openlocfilehash: 513fe618d32e3a3dcfadcf98134a927ddf629b86
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761800"
---
# <a name="atl-typedefs"></a>ATL tür tanımları

Etkin Şablon Kütüphanesi aşağıdaki tür tanımları içerir.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|Temel tür tanımı olarak tanımlanan [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|
|[_ATL_COM_MODULE](#_atl_com_module)|Temel tür tanımı olarak tanımlanan [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|
|[_ATL_MODULE](#_atl_module)|Temel tür tanımı olarak tanımlanan [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|
|[_ATL_WIN_MODULE](#_atl_win_module)|Temel tür tanımı olarak tanımlanan [_atl_wın_module70](../../atl/reference/atl-win-module70-structure.md)|
|[ATL_URL_PORT](#atl_url_port)|Tarafından kullanılan türü [CUrl](../../atl/reference/curl-class.md) bir bağlantı noktası numarası belirtmek için.|
|[CComDispatchDriver](#ccomdispatchdriver)|Bu sınıf, arabirim işaretçilerini COM yönetir.|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Uygun iş parçacığı kullanılan iş parçacığı modeli bağımsız olarak model yöntemleri çağırır.|
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Uygun iş parçacığı kullanılan iş parçacığı modeli bağımsız olarak model yöntemleri çağırır.|
|[CContainedWindow](#ccontainedwindow)|Bu sınıf, bir alt uzmanlaşması `CContainedWindowT`.|
|[CPath](#cpath)|Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CString`.|
|[CPathA](#cpatha)|Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CStringA`.|
|[CPathW](#cpathw)|Bir alt uzmanlaşması [CPathT](../../atl/reference/cpatht-class.md) kullanarak `CStringW`.|
|[CSimpleValArray](#csimplevalarray)|Basit türler depolamak için bir dizi temsil eder.|
|[DefaultThreadTraits](#defaultthreadtraits)|Varsayılan iş parçacığı nitelikler sınıfı.|
|[LPCURL](#lpcurl)|Bir sabit bir işaretçi [CUrl](../../atl/reference/curl-class.md) nesne.|
|[LPURL](#lpurl)|Bir işaretçi bir [CUrl](../../atl/reference/curl-class.md) nesne.|

##  <a name="_atl_base_module"></a>  _ATL_BASE_MODULE

_ATL_BASE_MODULE70 üzerinde temel bir typedef tanımlanır.

```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```

### <a name="remarks"></a>Açıklamalar

Her bir ATL projesinde kullanılır. Temel [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).

ATL 7.0 modül sınıfları parçası olan sınıflar _ATL_BASE_MODULE yapısından türetilir.  ATL modül sınıfları hakkında daha fazla bilgi için başvurmak [COM modülü sınıfları](../../atl/com-modules-classes.md).  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="_atl_com_module"></a>  _ATL_COM_MODULE

_ATL_COM_MODULE70 üzerinde temel bir typedef tanımlanır.

```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```

### <a name="remarks"></a>Açıklamalar

COM özellikleri kullanan ATL projeleri tarafından kullanılır. Temel [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="_atl_module"></a>  _ATL_MODULE

_ATL_MODULE70 üzerinde temel bir typedef tanımlanır.

```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**

### <a name="remarks"></a>Açıklamalar

Temel [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).

##  <a name="_atl_win_module"></a>  _ATL_WIN_MODULE

_Atl_wın_module70 üzerinde temel bir typedef tanımlanır.

```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
```

### <a name="remarks"></a>Açıklamalar

Pencereleme özellikleri kullanan bir ATL projesi tarafından kullanılır. Temel [_atl_wın_module70](../../atl/reference/atl-win-module70-structure.md).  

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

Bu sınıf, arabirim işaretçilerini COM yönetir.

```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="ccomglobalsthreadmodel"></a>  CComGlobalsThreadModel

Uygun iş parçacığı kullanılan iş parçacığı modeli bağımsız olarak model yöntemleri çağırır.

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

Uygulamanız tarafından kullanılan iş parçacığı modeline bağlı olarak **typedef** adı `CComGlobalsThreadModel` ya da başvurduğu [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Bu sınıf ek sağlamak `typedef` kritik bölüm sınıfı başvuru adları.

> [!NOTE]
> `CComGlobalsThreadModel` sınıf başvurmuyor [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

Kullanarak `CComGlobalsThreadModel` belirli bir iş parçacığı model sınıfı belirtmelerini serbest bırakır. Kullanılan iş parçacığı modeli bağımsız olarak, uygun yöntemleri çağrılmaz.

Ek olarak `CComGlobalsThreadModel`, ATL sağlar **typedef** adı [CComObjectThreadModel](#ccomobjectthreadmodel). Her tarafından başvurulan sınıfın `typedef` iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:

|typedef|Çoklu iş parçacığı oluşturma|Grup iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Kullanım `CComObjectThreadModel` içinde tek bir nesne sınıfı. Kullanım `CComGlobalsThreadModel` programınıza genel olarak kullanılabilen veya birden çok iş parçacığı arasında modülü kaynakları korumak istiyorsanız, bir nesnedeki.  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="ccomobjectthreadmodel"></a>  CComObjectThreadModel

Uygun iş parçacığı kullanılan iş parçacığı modeli bağımsız olarak model yöntemleri çağırır.

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

Uygulamanız tarafından kullanılan iş parçacığı modeline bağlı olarak `typedef` adı `CComObjectThreadModel` ya da başvurduğu [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Bu sınıf ek sağlamak `typedef` kritik bölüm sınıfı başvuru adları.

> [!NOTE]
> `CComObjectThreadModel` sınıf başvurmuyor [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

Kullanarak `CComObjectThreadModel` belirli bir iş parçacığı model sınıfı belirtmelerini serbest bırakır. Kullanılan iş parçacığı modeli bağımsız olarak, uygun yöntemleri çağrılmaz.

Ek olarak `CComObjectThreadModel`, ATL sağlar **typedef** adı [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Her tarafından başvurulan sınıfın **typedef** iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:

|typedef|Çoklu iş parçacığı oluşturma|Grup iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Kullanım `CComObjectThreadModel` içinde tek bir nesne sınıfı. Kullanım `CComGlobalsThreadModel` ya da bir nesnedeki programınızı veya birden çok iş parçacığı arasında modülü kaynakları korumak istediğinizde genel olarak kullanılabilir.  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="ccontainedwindow"></a>  CContainedWindow

Bu sınıf, bir alt uzmanlaşması `CContainedWindowT`.

```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

### <a name="remarks"></a>Açıklamalar

`CContainedWindow` bir alt uzmanlaşması olduğu [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md). Temel sınıf veya nitelikler değiştirmek istiyorsanız, kullanın `CContainedWindowT` doğrudan.

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

`CSimpleValArray` oluşturma ve yönetme basit veri türleri içeren diziler için sağlanır. Basit bir #define, [CSimpleArray](../../atl/reference/csimplearray-class.md).  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

##  <a name="lpcurl"></a>  LPCURL

Bir sabit bir işaretçi [CUrl](../../atl/reference/curl-class.md) nesne.

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

Geçerli proje birden çok iş parçacıklı CRT kullanıyorsa, DefaultThreadTraits CRTThreadTraits tanımlanır. Aksi halde Win32ThreadTraits kullanılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="lpurl"></a>  LPURL

Bir işaretçi bir [CUrl](../../atl/reference/curl-class.md) nesne.

```   
typedef CUrl* LPURL;   
```  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md)   
[İşlevleri](../../atl/reference/atl-functions.md)   
[Genel değişkenler](../../atl/reference/atl-global-variables.md)   
[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)   
[Makroları](../../atl/reference/atl-macros.md)   
