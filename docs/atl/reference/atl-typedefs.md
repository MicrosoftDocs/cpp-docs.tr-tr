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
ms.openlocfilehash: 10d11b2b6e78220c1c562d100ee7886026a94b22
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833874"
---
# <a name="atl-typedefs"></a>ATL Tür tanımları

Etkin Şablon kitaplığı aşağıdaki tür tanımlarını içerir.

|Genişletiyor|Açıklama|
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)temel alan bir typedef olarak tanımlanır.|
|[_ATL_COM_MODULE](#_atl_com_module)|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)temel alan bir typedef olarak tanımlanır.|
|[_ATL_MODULE](#_atl_module)|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)temel alan bir typedef olarak tanımlanır.|
|[_ATL_WIN_MODULE](#_atl_win_module)|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) tabanlı bir typedef olarak tanımlanır|
|[ATL_URL_PORT](#atl_url_port)|Bir bağlantı noktası numarası belirtmek için [kıvrımlı](../../atl/reference/curl-class.md) tarafından kullanılan tür.|
|[CComDispatchDriver](#ccomdispatchdriver)|Bu sınıf, COM arabirimi işaretçilerini yönetir.|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Kullanılan iş parçacığı modelinden bağımsız olarak uygun iş parçacığı modeli yöntemlerini çağırır.|
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Kullanılan iş parçacığı modelinden bağımsız olarak uygun iş parçacığı modeli yöntemlerini çağırır.|
|[CContainedWindow](#ccontainedwindow)|Bu sınıf, öğesinin bir özelleştirmesi `CContainedWindowT` .|
|[CPath](#cpath)|Kullanarak [CPathT](../../atl/reference/cpatht-class.md) özelleştirmesi `CString` .|
|[CPathA](#cpatha)|Kullanarak [CPathT](../../atl/reference/cpatht-class.md) özelleştirmesi `CStringA` .|
|[CPathW](#cpathw)|Kullanarak [CPathT](../../atl/reference/cpatht-class.md) özelleştirmesi `CStringW` .|
|[CSimpleValArray](#csimplevalarray)|Basit türleri depolamak için bir diziyi temsil eder.|
|[Defaultthreadnitelikler](#defaultthreadtraits)|Varsayılan iş parçacığı nitelikleri sınıfı.|
|[LPKıVRıK](#lpcurl)|Sabit [kıvrımlı](../../atl/reference/curl-class.md) nesne işaretçisi.|
|[LPURL](#lpurl)|Bir [kıvrımlı](../../atl/reference/curl-class.md) nesne işaretçisi.|

## <a name="_atl_base_module"></a><a name="_atl_base_module"></a> _ATL_BASE_MODULE

_ATL_BASE_MODULE70 temel alan bir typedef olarak tanımlanır.

```cpp
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>Açıklamalar

Her ATL projesinde kullanılır. [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)temel alır.

ATL 7,0 modül sınıflarının parçası olan sınıflar _ATL_BASE_MODULE yapısından türetilir.  ATL modül sınıfları hakkında daha fazla bilgi için bkz. [com modül sınıfları](../../atl/com-modules-classes.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="_atl_com_module"></a><a name="_atl_com_module"></a> _ATL_COM_MODULE

_ATL_COM_MODULE70 temel alan bir typedef olarak tanımlanır.

```cpp
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>Açıklamalar

COM özellikleri kullanan ATL projeleri tarafından kullanılır. [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)temel alır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="_atl_module"></a><a name="_atl_module"></a> _ATL_MODULE

_ATL_MODULE70 temel alan bir typedef olarak tanımlanır.

```cpp
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

### <a name="requirements"></a>Gereksinimler

**Üst bilgi**

### <a name="remarks"></a>Açıklamalar

[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)temel alır.

## <a name="_atl_win_module"></a><a name="_atl_win_module"></a> _ATL_WIN_MODULE

_ATL_WIN_MODULE70 temel alan bir typedef olarak tanımlanır.

```cpp
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>Açıklamalar

Pencereleme özellikleri kullanan tüm ATL projeleri tarafından kullanılır. [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)temel alır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atl_url_port"></a><a name="atl_url_port"></a> ATL_URL_PORT

Bir bağlantı noktası numarası belirtmek için [kıvrımlı](curl-class.md) tarafından kullanılan tür.

```cpp
typedef WORD ATL_URL_PORT;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a> CComDispatchDriver

Bu sınıf, COM arabirimi işaretçilerini yönetir.

```cpp
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a> CComGlobalsThreadModel

Kullanılan iş parçacığı modelinden bağımsız olarak uygun iş parçacığı modeli yöntemlerini çağırır.

```cpp
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

Uygulamanız tarafından kullanılan iş parçacığı modeline bağlı olarak **`typedef`** ad, `CComGlobalsThreadModel` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)'e başvurur. Bu sınıflar, **`typedef`** kritik bölüm sınıfına başvurmak için ek adlar sağlar.

> [!NOTE]
> `CComGlobalsThreadModel`[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)sınıfına başvurmuyor.

Kullanma `CComGlobalsThreadModel` , belirli bir iş parçacığı modeli sınıfı belirtmekten kurtarır. Kullanılan iş parçacığı modelinden bağımsız olarak, uygun yöntemler çağrılacaktır.

Buna ek olarak `CComGlobalsThreadModel` , ATL **`typedef`** [CComObjectThreadModel](#ccomobjectthreadmodel)adını da sağlar. Tarafından başvurulan sınıf, **`typedef`** Aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

| typedef|Tek iş parçacığı|Apartman iş parçacığı|Serbest iş parçacığı|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ; D = `CComMultiThreadModel`

`CComObjectThreadModel`Tek bir nesne sınıfı içinde kullanın. `CComGlobalsThreadModel`Programınız için genel olarak kullanılabilen bir nesne veya birden çok iş parçacığı arasında modül kaynaklarını korumak istediğinizde kullanın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a> CComObjectThreadModel

Kullanılan iş parçacığı modelinden bağımsız olarak uygun iş parçacığı modeli yöntemlerini çağırır.

```cpp
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

Uygulamanız tarafından kullanılan iş parçacığı modeline bağlı olarak **`typedef`** ad, `CComObjectThreadModel` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)'e başvurur. Bu sınıflar, **`typedef`** kritik bölüm sınıfına başvurmak için ek adlar sağlar.

> [!NOTE]
> `CComObjectThreadModel`[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)sınıfına başvurmuyor.

Kullanma `CComObjectThreadModel` , belirli bir iş parçacığı modeli sınıfı belirtmekten kurtarır. Kullanılan iş parçacığı modelinden bağımsız olarak, uygun yöntemler çağrılacaktır.

Buna ek olarak `CComObjectThreadModel` , ATL **`typedef`** [CComGlobalsThreadModel](#ccomglobalsthreadmodel)adını da sağlar. Tarafından başvurulan sınıf, **`typedef`** Aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

| typedef|Tek iş parçacığı|Apartman iş parçacığı|Serbest iş parçacığı|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ; D = `CComMultiThreadModel`

`CComObjectThreadModel`Tek bir nesne sınıfı içinde kullanın. `CComGlobalsThreadModel`Programınızın genel olarak kullanabildiği bir nesne veya birden çok iş parçacığı arasında modül kaynaklarını korumak istediğinizde kullanın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccontainedwindow"></a><a name="ccontainedwindow"></a> CContainedWindow

Bu sınıf, öğesinin bir özelleştirmesi `CContainedWindowT` .

```cpp
typedef CContainedWindowT<CWindow> CContainedWindow;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

### <a name="remarks"></a>Açıklamalar

`CContainedWindow` , [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)'in bir özelleştirmesi. Temel sınıf veya nitelikleri değiştirmek istiyorsanız, `CContainedWindowT` doğrudan kullanın.

## <a name="cpath"></a><a name="cpath"></a> CPath

Kullanarak [CPathT](../../atl/reference/cpatht-class.md) özelleştirmesi `CString` .

```cpp
typedef CPathT<CString> CPath;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath. h

## <a name="cpatha"></a><a name="cpatha"></a> CPathA

Kullanarak [CPathT](../../atl/reference/cpatht-class.md) özelleştirmesi `CStringA` .

```cpp
typedef CPathT<CStringA> CPathA;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath. h

## <a name="cpathw"></a><a name="cpathw"></a> CPathW

Kullanarak [CPathT](../../atl/reference/cpatht-class.md) özelleştirmesi `CStringW` .

```cpp
typedef ATL::CPathT<CStringW> CPathW;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath. h

## <a name="csimplevalarray"></a><a name="csimplevalarray"></a> CSimpleValArray

Basit türleri depolamak için bir diziyi temsil eder.

```cpp
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>Açıklamalar

`CSimpleValArray` basit veri türleri içeren diziler oluşturmak ve yönetmek için sağlanır. [CSimpleArray](../../atl/reference/csimplearray-class.md)basit bir #define.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpcoll. h

## <a name="lpcurl"></a><a name="lpcurl"></a> LPKıVRıK

Sabit [kıvrımlı](../../atl/reference/curl-class.md) nesne işaretçisi.

```cpp
typedef const CUrl* LPCURL;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="defaultthreadtraits"></a><a name="defaultthreadtraits"></a> Defaultthreadnitelikler

Varsayılan iş parçacığı nitelikleri sınıfı.

### <a name="syntax"></a>Syntax

```cpp
#if defined(_MT)
   typedef CRTThreadTraits DefaultThreadTraits;
#else
   typedef Win32ThreadTraits DefaultThreadTraits;
#endif
```

## <a name="remarks"></a>Açıklamalar

Geçerli proje çok iş parçacıklı CRT kullanıyorsa, Defaultthreadnitelikler Crtthreadnitelikler olarak tanımlanır. Aksi halde, Win32ThreadTraits kullanılır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="lpurl"></a><a name="lpurl"></a> LPURL

Bir [kıvrımlı](../../atl/reference/curl-class.md) nesne işaretçisi.

```cpp
typedef CUrl* LPURL;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)<br/>
[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Genel değişkenler](../../atl/reference/atl-global-variables.md)<br/>
[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)<br/>
[Makrolar](../../atl/reference/atl-macros.md)
