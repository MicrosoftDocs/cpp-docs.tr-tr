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
ms.openlocfilehash: 64b4124ba3c60fdcb53fc29c7b791c0f73a49579
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376232"
---
# <a name="runtimeclass-class"></a>RuntimeClass Sınıfı

Belirtilen arabirimleri devralan ve belirtilen Windows Runtime, klasik COM ve zayıf başvuru desteği sağlayan bir WinRT veya COM sınıfını temsil eder.

Bu sınıf WinRT ve COM sınıflarının ortak uygulamasını sağlar, `AddRef` `Release` modülün `QueryInterface`referans sayısını yönetir ve etkinleştirilebilir nesneler için sınıf fabrikası sağlamak için destek sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Parametreler

*classFlags*<br/>
İsteğe bağlı parametre. Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değerlerinin birleşimi. Makro, `__WRL_CONFIGURATION_LEGACY__` projedeki tüm çalışma zamanı sınıfları için classFlags'in varsayılan değerini değiştirmek için tanımlanabilir. Tanımlanmışsa, RuntimeClass örnekleri varsayılan olarak çevik değildir. Tanımlanmadığında, RuntimeClass örnekleri varsayılan olarak çeviktir. Belirsizlikten kaçınmak için her `Microsoft::WRL::FtmBase` `TInterfaces` zaman `RuntimeClassType::InhibitFtmBase`in veya . Unutmayın, InhibitFtmBase ve FtmBase her ikisi de kullanılırsa nesne çevik olacaktır.

*TInterfaces*<br/>
Nesnenin ötesinde `IUnknown`uyguladığı arabirimler `IInspectable` veya [RuntimeClassType](runtimeclasstype-enumeration.md)tarafından denetlenen diğer arabirimler listesi. Ayrıca, özellikle `Microsoft::WRL::FtmBase` nesneyi çevik yapmak ve uygulanmasına `IMarshal`neden olmak için türetilecek diğer sınıfları listeleyebilir.

## <a name="members"></a>Üyeler

`RuntimeClassInitialize`<br/>
`MakeAndInitialize` Şablon işlevi nesneyi oluşturmak için kullanılırsa nesneyi başharfleyen bir işlev. Nesne başarıyla başharfe S_OK veya başlatma başarısız olduysa bir COM hata kodu döndürür. COM hata kodu, `MakeAndInitialize`'nin döndürme değeri olarak yayılır. Şablon işlevi `RuntimeClassInitialize` nesneyi oluşturmak için kullanılıyorsa yöntemin çağrılmadığını unutmayın. `Make`

### <a name="public-constructors"></a>Ortak Oluşturucular

| Adı                                               | Açıklama                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass::RuntimeClass](#runtimeclass)        | Sınıfın geçerli örneğini `RuntimeClass` başolarak karşılar.   |
| [RuntimeClass::~RuntimeClass](#tilde-runtimeclass) | Sınıfın geçerli örneğini `RuntimeClass` deinitialize eder. |

### <a name="public-methods"></a>Ortak Yöntemler

| Adı                                                      | Açıklama                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass::AddRef](#addref)                           | Geçerli `RuntimeClass` nesne için başvuru sayısını artırımı.                              |
| [RuntimeClass::DecrementReference](#decrementreference)   | Geçerli `RuntimeClass` nesne için başvuru sayısını eriter.                              |
| [RuntimeClass::GetIids](#getiids)                         | Geçerli `RuntimeClass` nesne tarafından uygulanan arabirim dislerini içerebilen bir dizi alır. |
| [RuntimeClass::GetRuntimeClassName](#getruntimeclassname) | Geçerli `RuntimeClass` nesnenin çalışma zamanı sınıf adını alır.                                  |
| [RuntimeClass::GetTrustLevel](#gettrustlevel)             | Geçerli `RuntimeClass` nesnenin güven düzeyini alır.                                         |
| [RuntimeClass::GetWeakReference](#getweakreference)       | Geçerli `RuntimeClass` nesne için zayıf başvuru nesnesine bir işaretçi alır.                 |
| [RuntimeClass::InternalAddRef](#internaladdref)           | Geçerli `RuntimeClass` nesneye başvuru sayısını artırımı.                               |
| [RuntimeClass::QueryInterface](#queryinterface)           | Belirtilen arabirim kimliği için bir işaretçi alır.                                                 |
| [RuntimeClass::Sürüm](#release)                         | Geçerli `RuntimeClass` nesne üzerinde bir COM Release işlemi gerçekleştirir.                             |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

Bu bir uygulama ayrıntısI.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a>RuntimeClass::~RuntimeClass

Sınıfın geçerli örneğini `RuntimeClass` deinitialize eder.

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a>RuntimeClass::AddRef

Geçerli `RuntimeClass` nesne için başvuru sayısını artırımı.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a>RuntimeClass::DecrementReference

Geçerli `RuntimeClass` nesne için başvuru sayısını eriter.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="runtimeclassgetiids"></a><a name="getiids"></a>RuntimeClass::GetIids

Geçerli `RuntimeClass` nesne tarafından uygulanan arabirim dislerini içerebilen bir dizi alır.

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametreler

*iidSay*<br/>
Bu işlem tamamlandığında, dizi *iids*elemanlarının toplam sayısı.

*iids*<br/>
Bu işlem tamamlandığında, arabirim iLikleri dizisiiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_OUTOFMEMORY.

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a>RuntimeClass::GetRuntimeClassName

Geçerli `RuntimeClass` nesnenin çalışma zamanı sınıf adını alır.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, çalışma zamanı sınıf adı.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Tanımlanmamışsa `__WRL_STRICT__` veya `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` tanımlanmamışsa bir ileri savunma hatası yayımlanır.

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a>RuntimeClass::GetTrustLevel

Geçerli `RuntimeClass` nesnenin güven düzeyini alır.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parametreler

*güvenLvl*<br/>
Bu işlem tamamlandığında, geçerli `RuntimeClass` nesnenin güven düzeyi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

### <a name="remarks"></a>Açıklamalar

Tanımlanmamışsa `__WRL_STRICT__` veya `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` tanımlanmamışsa bir ileri savunma hatası yayımlanır.

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a>RuntimeClass::GetWeakReference

Geçerli `RuntimeClass` nesne için zayıf başvuru nesnesine bir işaretçi alır.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Parametreler

*Weakreference*<br/>
Bu işlem tamamlandığında, zayıf bir başvuru nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a>RuntimeClass::InternalAddRef

Geçerli `RuntimeClass` nesneye başvuru sayısını artırımı.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan başvuru sayısı.

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a>RuntimeClass::QueryInterface

Belirtilen arabirim kimliği için bir işaretçi alır.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arayüz kimliği.

*ppvNesne*<br/>
Bu opereation tamamlandığında, *riid* parametresi tarafından belirtilen arabirime bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="runtimeclassrelease"></a><a name="release"></a>RuntimeClass::Sürüm

Geçerli `RuntimeClass` nesne üzerinde bir COM Release işlemi gerçekleştirir.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Başvuru sayısı sıfır olursa, `RuntimeClass` nesne silinir.

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a>RuntimeClass::RuntimeClass

Sınıfın geçerli örneğini `RuntimeClass` başolarak karşılar.

```cpp
RuntimeClass();
```
