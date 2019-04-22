---
title: RuntimeClass Sınıfı
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: d45fe7c6d794f216da93ffbd95dbb7058d3336f3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787778"
---
# <a name="runtimeclass-class"></a>RuntimeClass Sınıfı

Belirtilen Windows çalışma zamanı klasik COM ve zayıf başvuru desteği sağlar ve belirtilen arabirimlerden devralan WinRT veya COM bir sınıfı temsil eder.

Bu sınıf uygulamasını sağlayan, WinRT ve COM sınıfların ortak uygulamasını sağlar `QueryInterface`, `AddRef`, `Release` vb., modülün başvuru sayısını yönetir ve sınıf üreteci için sağlama için destek sunmaktadır nesneleri etkinleştirilebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Parametreler

*classFlags*<br/>
İsteğe bağlı parametre. Bir veya daha fazla birleşimi [RuntimeClassType](runtimeclasstype-enumeration.md) sabit listesi değerleri. `__WRL_CONFIGURATION_LEGACY__` ClassFlags projedeki tüm çalışma zamanı sınıflar için varsayılan değeri değiştirmek için makro tanımlanabilir. Tanımlı değilse RuntimeClass varsayılan olmayan Çevik örnekleridir. RuntimeClass örnekleri, tanımlı değil, varsayılan olarak Çevik. Her zaman belirsizlik belirtmeniz önlemek `Microsoft::WRL::FtmBase` içinde `TInterfaces` veya `RuntimeClassType::InhibitFtmBase`. Hem de nesne kullanılan InhibitFtmBase ve FtmBase olup olmadığını Not, Çevik olacaktır.

*TInterfaces*<br/>
Arabirimlerin listesini ötesinde nesne uygulayan `IUnknown`, `IInspectable` veya diğer arabirimleri tarafından denetlenen [RuntimeClassType](runtimeclasstype-enumeration.md). Diğer sınıflar, özellikle türetilmesi listeleyebilir `Microsoft::WRL::FtmBase` nesne Çevik olun ve uygulamak neden `IMarshal`.

## <a name="members"></a>Üyeler

`RuntimeClassInitialize`<br/>
Bir işlev, nesne başlatır `MakeAndInitialize` şablon işlevi, nesneyi oluşturmak için kullanılır. Başlatma başarısız olursa nesne başarıyla başlatıldı, S_OK veya bir COM hata kodu döndürür. COM hata kodu, dönüş değeri olarak yayılır `MakeAndInitialize`. Unutmayın `RuntimeClassInitialize` yönteminin çağrılmaması durumunda `Make` şablon işlevi, nesneyi oluşturmak için kullanılır.

### <a name="public-constructors"></a>Ortak Oluşturucular

| Ad                                               | Açıklama                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass::RuntimeClass](#runtimeclass)        | Geçerli örneğinin başlatır `RuntimeClass` sınıfı.   |
| [RuntimeClass:: ~ RuntimeClass](#tilde-runtimeclass) | Geçerli örneğinin başlatmasını geri alır `RuntimeClass` sınıfı. |

### <a name="public-methods"></a>Ortak Yöntemler

| Ad                                                      | Açıklama                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass::AddRef](#addref)                           | Geçerli başvuru sayısını artırır `RuntimeClass` nesne.                              |
| [RuntimeClass::DecrementReference](#decrementreference)   | Başvuru için geçerli sayısını azaltır `RuntimeClass` nesne.                              |
| [Runtimeclass::getıids](#getiids)                         | Kimlikleri geçerli tarafından uygulanan arabirimi içerebilir bir dizisini alır `RuntimeClass` nesne. |
| [RuntimeClass::GetRuntimeClassName](#getruntimeclassname) | Geçerli çalışma zamanı sınıf adını alır `RuntimeClass` nesne.                                  |
| [RuntimeClass::GetTrustLevel](#gettrustlevel)             | Geçerli güven düzeyine alır `RuntimeClass` nesne.                                         |
| [RuntimeClass::GetWeakReference](#getweakreference)       | Geçerli zayıf başvuru nesnesine bir işaretçi alır `RuntimeClass` nesne.                 |
| [Runtimeclass::ınternaladdref](#internaladdref)           | Geçerli başvuru sayısını artırır `RuntimeClass` nesne.                               |
| [Runtimeclass::QueryInterface](#queryinterface)           | Belirtilen arabirim kimliği. bir işaretçi alır.                                                 |
| [RuntimeClass::Release](#release)                         | Geçerli bir COM yayınında işlemi gerçekleştirir `RuntimeClass` nesne.                             |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

Bir uygulama ayrıntısı budur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="tilde-runtimeclass"></a>RuntimeClass:: ~ RuntimeClass

Geçerli örneğinin başlatmasını geri alır `RuntimeClass` sınıfı.

```cpp
virtual ~RuntimeClass();
```

## <a name="addref"></a>RuntimeClass::AddRef

Geçerli başvuru sayısını artırır `RuntimeClass` nesne.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="decrementreference"></a>RuntimeClass::DecrementReference

Başvuru için geçerli sayısını azaltır `RuntimeClass` nesne.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="getiids"></a>Runtimeclass::getıids

Kimlikleri geçerli tarafından uygulanan arabirimi içerebilir bir dizisini alır `RuntimeClass` nesne.

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametreler

*Iidcount*<br/>
Bu işlem tamamlandığında, toplam sayısı dizideki öğelerin *IID'leri*.

*IID'leri*<br/>
Bu işlem tamamlandığında arabirim kimlikleri dizisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_OUTOFMEMORY.

## <a name="getruntimeclassname"></a>RuntimeClass::GetRuntimeClassName

Geçerli çalışma zamanı sınıf adını alır `RuntimeClass` nesne.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, çalışma zamanı sınıf adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Assert hata durumunda yayıldığını `__WRL_STRICT__` veya `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` tanımlanmadı.

## <a name="gettrustlevel"></a>RuntimeClass::GetTrustLevel

Geçerli güven düzeyine alır `RuntimeClass` nesne.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parametreler

*trustLvl*<br/>
Bu işlem tamamlandığında, geçerli güven düzeyine `RuntimeClass` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

### <a name="remarks"></a>Açıklamalar

Assert hata durumunda yayıldığını `__WRL_STRICT__` veya `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` tanımlanmadı.

## <a name="getweakreference"></a>RuntimeClass::GetWeakReference

Geçerli zayıf başvuru nesnesine bir işaretçi alır `RuntimeClass` nesne.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Parametreler

*weakReference*<br/>
Bu işlem tamamlandığında zayıf başvuru nesnesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

## <a name="internaladdref"></a>Runtimeclass::ınternaladdref

Geçerli başvuru sayısını artırır `RuntimeClass` nesne.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen başvuru sayısı.

## <a name="queryinterface"></a>Runtimeclass::QueryInterface

Belirtilen arabirim kimliği. bir işaretçi alır.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
Bir arabirim kimliği.

*ppvObject*<br/>
Bu opereation tamamlandığında tarafından belirtilen arabirim işaretçisi *riid* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="release"></a>RuntimeClass::Release

Geçerli bir COM yayınında işlemi gerçekleştirir `RuntimeClass` nesne.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Başvuru sayısı sıfır olduğunda `RuntimeClass` nesnesi silinir.

## <a name="runtimeclass"></a>RuntimeClass::RuntimeClass

Geçerli örneğinin başlatır `RuntimeClass` sınıfı.

```cpp
RuntimeClass();
```
