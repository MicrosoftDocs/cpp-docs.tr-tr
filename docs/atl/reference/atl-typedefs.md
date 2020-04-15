---
title: ATL Tür tanımları
ms.date: 11/04/2016
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
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
ms.openlocfilehash: 5548bee36ac52dbd6add31241714b0404289be45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319189"
---
# <a name="atl-typedefs"></a>ATL Tür tanımları

Etkin Şablon Kitaplığı aşağıdaki typedefs içerir.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)dayalı bir typedef olarak tanımlanır.|
|[_ATL_COM_MODULE](#_atl_com_module)|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)dayalı bir typedef olarak tanımlanır.|
|[_ATL_MODULE](#_atl_module)|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)dayalı bir typedef olarak tanımlanır.|
|[_ATL_WIN_MODULE](#_atl_win_module)|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) dayalı typedef olarak tanımlanır|
|[ATL_URL_PORT](#atl_url_port)|Bir bağlantı noktası numarası belirtmek için [CUrl](../../atl/reference/curl-class.md) tarafından kullanılan tür.|
|[CcomDispatchDriver](#ccomdispatchdriver)|Bu sınıf, COM arabirim işaretçileri yönetir.|
|[Ccomglobalsthreadmodel](#ccomglobalsthreadmodel)|Kullanılan iş parçacığı modeline bakılmaksızın uygun iş parçacığı modeli yöntemlerini çağırır.|
|[Ccomobjectthreadmodel](#ccomobjectthreadmodel)|Kullanılan iş parçacığı modeline bakılmaksızın uygun iş parçacığı modeli yöntemlerini çağırır.|
|[CContainedWindow](#ccontainedwindow)|Bu sınıf bir uzmanlık `CContainedWindowT`olduğunu .|
|[CPath](#cpath)|[CPathT'nin](../../atl/reference/cpatht-class.md) uzmanlık `CString`alanı .|
|[Cpatha](#cpatha)|[CPathT'nin](../../atl/reference/cpatht-class.md) uzmanlık `CStringA`alanı .|
|[CPathW](#cpathw)|[CPathT'nin](../../atl/reference/cpatht-class.md) uzmanlık `CStringW`alanı .|
|[CSimpleValArray](#csimplevalarray)|Basit türleri depolamak için bir dizitemsil eder.|
|[Varsayılan ThreadTraits](#defaultthreadtraits)|Varsayılan iş parçacığı özellikleri sınıfı.|
|[LPCURL](#lpcurl)|Sabit bir [CUrl](../../atl/reference/curl-class.md) nesnesine işaretçi.|
|[LPURL](#lpurl)|[CUrl](../../atl/reference/curl-class.md) nesnesine işaretçi.|

## <a name="_atl_base_module"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE

_ATL_BASE_MODULE70 dayalı bir typedef olarak tanımlanır.

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>Açıklamalar

Her ATL projesinde kullanılır. [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)dayanarak.

ATL 7.0 Modül Sınıflarının bir parçası olan sınıflar _ATL_BASE_MODULE yapısından kaynaklanır.  ATL Modül Sınıfları hakkında daha fazla bilgi için [COM Modül Sınıfları'na](../../atl/com-modules-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="_atl_com_module"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE

_ATL_COM_MODULE70 dayalı bir typedef olarak tanımlanır.

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>Açıklamalar

COM özelliklerini kullanan ATL projeleri tarafından kullanılır. [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)dayanarak.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="_atl_module"></a><a name="_atl_module"></a>_ATL_MODULE

_ATL_MODULE70 dayalı bir typedef olarak tanımlanır.

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:**

### <a name="remarks"></a>Açıklamalar

[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)dayanarak.

## <a name="_atl_win_module"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE

_ATL_WIN_MODULE70 dayalı bir typedef olarak tanımlanır.

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>Açıklamalar

Pencereleme özelliklerini kullanan tüm ATL projeleri tarafından kullanılır. [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)dayanarak.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atl_url_port"></a><a name="atl_url_port"></a>ATL_URL_PORT

Bir bağlantı noktası numarası belirtmek için [CUrl](curl-class.md) tarafından kullanılan tür.

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>CcomDispatchDriver

Bu sınıf, COM arabirim işaretçileri yönetir.

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>Ccomglobalsthreadmodel

Kullanılan iş parçacığı modeline bakılmaksızın uygun iş parçacığı modeli yöntemlerini çağırır.

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

Uygulamanız tarafından kullanılan iş parçacığı modeline bağlı `CComGlobalsThreadModel` olarak, **typedef** adı [ya CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)başvurur. Bu sınıflar, `typedef` kritik bir bölüm sınıfına başvurmak için ek adlar sağlar.

> [!NOTE]
> `CComGlobalsThreadModel`sınıf [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)başvuru yok.

Kullanmak, `CComGlobalsThreadModel` belirli bir iş parçacığı modeli sınıfı belirtmekten sizi kurtarır. Kullanılan iş parçacığı modeli ne olursa olsun, uygun yöntemler çağrılacaktır.

Buna ek `CComGlobalsThreadModel`olarak, ATL **typedef** adı [CComObjectThreadModel](#ccomobjectthreadmodel)sağlar. Her biri `typedef` tarafından başvurulan sınıf, aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

| typedef|Tek iş parçacığı|Daire diş ipliği|Serbest iş parçacığı|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`; M=`CComMultiThreadModel`

Tek `CComObjectThreadModel` bir nesne sınıfı içinde kullanın. Programınızda genel olarak kullanılabilen bir nesnede veya modül kaynaklarını birden çok iş parçacığı üzerinden korumak istediğinizde kullanın. `CComGlobalsThreadModel`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>Ccomobjectthreadmodel

Kullanılan iş parçacığı modeline bakılmaksızın uygun iş parçacığı modeli yöntemlerini çağırır.

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

Uygulamanız tarafından kullanılan iş parçacığı modeline `typedef` `CComObjectThreadModel` bağlı olarak, ad ya [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)başvurur. Bu sınıflar, `typedef` kritik bir bölüm sınıfına başvurmak için ek adlar sağlar.

> [!NOTE]
> `CComObjectThreadModel`sınıf [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)başvuru yok.

Kullanmak, `CComObjectThreadModel` belirli bir iş parçacığı modeli sınıfı belirtmekten sizi kurtarır. Kullanılan iş parçacığı modeli ne olursa olsun, uygun yöntemler çağrılacaktır.

Buna ek `CComObjectThreadModel`olarak, ATL **typedef** adı [CComGlobalsThreadModel](#ccomglobalsthreadmodel)sağlar. Her **typedef** tarafından başvurulan sınıf, aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

| typedef|Tek iş parçacığı|Daire diş ipliği|Serbest iş parçacığı|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`; M=`CComMultiThreadModel`

Tek `CComObjectThreadModel` bir nesne sınıfı içinde kullanın. Programınız için genel olarak kullanılabilen bir nesnede veya modül kaynaklarını birden çok iş parçacığı üzerinden korumak istediğinizde kullanın. `CComGlobalsThreadModel`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccontainedwindow"></a><a name="ccontainedwindow"></a>CContainedWindow

Bu sınıf bir uzmanlık `CContainedWindowT`olduğunu .

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

### <a name="remarks"></a>Açıklamalar

`CContainedWindow`[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)bir uzmanlık olduğunu. Taban sınıfı veya özellikleri değiştirmek istiyorsanız, `CContainedWindowT` doğrudan kullanın.

## <a name="cpath"></a><a name="cpath"></a>CPath

[CPathT'nin](../../atl/reference/cpatht-class.md) uzmanlık `CString`alanı .

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath.h

## <a name="cpatha"></a><a name="cpatha"></a>Cpatha

[CPathT'nin](../../atl/reference/cpatht-class.md) uzmanlık `CStringA`alanı .

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath.h

## <a name="cpathw"></a><a name="cpathw"></a>CPathW

[CPathT'nin](../../atl/reference/cpatht-class.md) uzmanlık `CStringW`alanı .

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath.h

## <a name="csimplevalarray"></a><a name="csimplevalarray"></a>CSimpleValArray

Basit türleri depolamak için bir dizitemsil eder.

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>Açıklamalar

`CSimpleValArray`basit veri türleri içeren diziler oluşturmak ve yönetmek için sağlanır. Bu [CSimpleArray](../../atl/reference/csimplearray-class.md)basit bir #define.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="lpcurl"></a><a name="lpcurl"></a>LPCURL

Sabit bir [CUrl](../../atl/reference/curl-class.md) nesnesine işaretçi.

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="defaultthreadtraits"></a><a name="defaultthreadtraits"></a>Varsayılan ThreadTraits

Varsayılan iş parçacığı özellikleri sınıfı.

### <a name="syntax"></a>Sözdizimi

```
#if defined(_MT)
   typedef CRTThreadTraits DefaultThreadTraits;
#else
   typedef Win32ThreadTraits DefaultThreadTraits;
#endif
```

## <a name="remarks"></a>Açıklamalar

Geçerli proje çok iş parçacığı CRT kullanıyorsa, DefaultThreadTraits CRTThreadTraits olarak tanımlanır. Aksi takdirde, Win32ThreadTraits kullanılır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="lpurl"></a><a name="lpurl"></a>LPURL

[CUrl](../../atl/reference/curl-class.md) nesnesine işaretçi.

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)<br/>
[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Global Değişkenler](../../atl/reference/atl-global-variables.md)<br/>
[Sınıflar ve structs](../../atl/reference/atl-classes.md)<br/>
[Makrolar](../../atl/reference/atl-macros.md)
