---
description: 'Daha fazla bilgi edinin: RuntimeClass Sınıfı'
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
ms.openlocfilehash: f62eec0b5ac9b8fc8ecac390ea07077743fdcb51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330758"
---
# <a name="runtimeclass-class"></a>RuntimeClass Sınıfı

Belirtilen arabirimleri devralan bir WinRT veya COM sınıfını temsil eder ve belirtilen Windows Çalışma Zamanı, klasik COM ve zayıf başvuru desteğini sağlar.

Bu sınıf,,, vb. uygulamasını sağlayan WinRT ve com sınıflarının ortak bir uygulamasını `QueryInterface` sağlar `AddRef` `Release` ve modülün başvuru sayısını yönetir ve etkinleştirilebilir nesneleri için sınıf fabrikası sağlama desteğine sahiptir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Parametreler

*classFlags*<br/>
İsteğe bağlı parametre. Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değerinin birleşimi. `__WRL_CONFIGURATION_LEGACY__`Makro, projedeki tüm çalışma zamanı sınıfları Için classFlags varsayılan değerini değiştirmek üzere tanımlanabilir. Tanımlanmışsa, RuntimeClass örnekleri varsayılan olarak çevik değildir. Tanımlanmadığında, RuntimeClass örnekleri varsayılan olarak çevik olarak işlenir. Belirsizlik olmaması için, veya ' de öğesini her zaman belirtin `Microsoft::WRL::FtmBase` `TInterfaces` `RuntimeClassType::InhibitFtmBase` . Bunun her ikisi de varsa, ' nin ve FtmBase 'in her ikisi de kullanılıyorsa, bu nesnenin çevik olacağını aklınızda görürsünüz.

*Tınterfaces*<br/>
Nesnenin ötesinde uyguladığı arabirimlerin listesi `IUnknown` `IInspectable` veya [RuntimeClassType](runtimeclasstype-enumeration.md)tarafından denetlenen diğer arabirimler. Ayrıca, özellikle de `Microsoft::WRL::FtmBase` nesneyi çevik hale getirmek ve uygulamaya yol açmak için türetilmiş diğer sınıfları listeleyebilir `IMarshal` .

## <a name="members"></a>Üyeler

`RuntimeClassInitialize`<br/>
`MakeAndInitialize`Nesneyi oluşturmak için şablon işlevi kullanılıyorsa nesneyi Başlatan bir işlev. Nesne başarıyla başlatılmışsa S_OK veya başlatma başarısız olursa bir COM hata kodu döndürür. COM hata kodu, dönüş değeri olarak dağıtılır `MakeAndInitialize` . `RuntimeClassInitialize` `Make` Nesne oluşturmak için şablon işlevi kullanılıyorsa yönteminin çağrılmadığını unutmayın.

### <a name="public-constructors"></a>Ortak Oluşturucular

| Ad                                               | Açıklama                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass:: RuntimeClass](#runtimeclass)        | Sınıfın geçerli örneğini başlatır `RuntimeClass` .   |
| [RuntimeClass:: ~ RuntimeClass](#tilde-runtimeclass) | Sınıfın geçerli örneğini kaldırır `RuntimeClass` . |

### <a name="public-methods"></a>Ortak Yöntemler

| Ad                                                      | Açıklama                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass:: AddRef](#addref)                           | Geçerli nesne için başvuru sayısını artırır `RuntimeClass` .                              |
| [RuntimeClass::D ecrementReference](#decrementreference)   | Geçerli nesne için başvuru sayısını azaltır `RuntimeClass` .                              |
| [RuntimeClass:: Getııds](#getiids)                         | Geçerli nesne tarafından uygulanan arabirim kimliklerini içerebilen bir dizi alır `RuntimeClass` . |
| [RuntimeClass:: GetRuntimeClassName](#getruntimeclassname) | Geçerli nesnenin çalışma zamanı sınıf adını alır `RuntimeClass` .                                  |
| [RuntimeClass:: GetTrustLevel](#gettrustlevel)             | Geçerli nesnenin güven düzeyini alır `RuntimeClass` .                                         |
| [RuntimeClass:: GetWeakReference](#getweakreference)       | Geçerli nesne için zayıf başvuru nesnesine bir işaretçi alır `RuntimeClass` .                 |
| [RuntimeClass:: InternalAddRef](#internaladdref)           | Başvuru sayısını geçerli `RuntimeClass` nesneye yükseltir.                               |
| [RuntimeClass:: QueryInterface](#queryinterface)           | Belirtilen arabirim KIMLIĞINE bir işaretçi alır.                                                 |
| [RuntimeClass:: Release](#release)                         | Geçerli nesne üzerinde bir COM serbest bırakma işlemi gerçekleştirir `RuntimeClass` .                             |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

Bu bir uygulama ayrıntısıyla belirlenir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a> RuntimeClass:: ~ RuntimeClass

Sınıfın geçerli örneğini kaldırır `RuntimeClass` .

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a> RuntimeClass:: AddRef

Geçerli nesne için başvuru sayısını artırır `RuntimeClass` .

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a> RuntimeClass::D ecrementReference

Geçerli nesne için başvuru sayısını azaltır `RuntimeClass` .

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="runtimeclassgetiids"></a><a name="getiids"></a> RuntimeClass:: Getııds

Geçerli nesne tarafından uygulanan arabirim kimliklerini içerebilen bir dizi alır `RuntimeClass` .

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametreler

*IidCount*<br/>
Bu işlem tamamlandığında, dizi *IIDS* içindeki toplam öğe sayısı.

*IID*<br/>
Bu işlem tamamlandığında, bir arabirim kimliği dizisine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_OUTOFMEMORY.

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a> RuntimeClass:: GetRuntimeClassName

Geçerli nesnenin çalışma zamanı sınıf adını alır `RuntimeClass` .

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, çalışma zamanı sınıf adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bir onaylama hatası, `__WRL_STRICT__` veya tanımlanmamışsa yayılır `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` .

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a> RuntimeClass:: GetTrustLevel

Geçerli nesnenin güven düzeyini alır `RuntimeClass` .

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parametreler

*trustLvl*<br/>
Bu işlem tamamlandığında, geçerli nesnenin güven düzeyi `RuntimeClass` .

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

### <a name="remarks"></a>Açıklamalar

Bir onaylama hatası, `__WRL_STRICT__` veya tanımlanmamışsa yayılır `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` .

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a> RuntimeClass:: GetWeakReference

Geçerli nesne için zayıf başvuru nesnesine bir işaretçi alır `RuntimeClass` .

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Parametreler

*weakReference*<br/>
Bu işlem tamamlandığında, zayıf başvuru nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a> RuntimeClass:: InternalAddRef

Başvuru sayısını geçerli `RuntimeClass` nesneye yükseltir.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen başvuru sayısı.

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a> RuntimeClass:: QueryInterface

Belirtilen arabirim KIMLIĞINE bir işaretçi alır.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*ppvObject*<br/>
Bu işlem tamamlandığında, *riıd* parametresi tarafından belirtilen arabirime yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="runtimeclassrelease"></a><a name="release"></a> RuntimeClass:: Release

Geçerli nesne üzerinde bir COM serbest bırakma işlemi gerçekleştirir `RuntimeClass` .

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Başvuru sayısı sıfır olursa, `RuntimeClass` nesne silinir.

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a> RuntimeClass:: RuntimeClass

Sınıfın geçerli örneğini başlatır `RuntimeClass` .

```cpp
RuntimeClass();
```
