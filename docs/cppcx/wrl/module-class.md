---
title: Modül Sınıfı
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
- module/Microsoft::WRL::Module::Create
- module/Microsoft::WRL::Module::DecrementObjectCount
- module/Microsoft::WRL::Module::GetActivationFactory
- module/Microsoft::WRL::Module::GetClassObject
- module/Microsoft::WRL::Module::GetModule
- module/Microsoft::WRL::Module::GetObjectCount
- module/Microsoft::WRL::Module::IncrementObjectCount
- module/Microsoft::WRL::Module::Module
- module/Microsoft::WRL::Module::objectCount_Data
- module/Microsoft::WRL::Module::RegisterCOMObject
- module/Microsoft::WRL::Module::RegisterObjects
- module/Microsoft::WRL::Module::RegisterWinRTObject
- module/Microsoft::WRL::Module::releaseNotifier_
- module/Microsoft::WRL::Module::Terminate
- module/Microsoft::WRL::Module::~Module
- module/Microsoft::WRL::Module::UnregisterCOMObject
- module/Microsoft::WRL::Module::UnregisterObjects
- module/Microsoft::WRL::Module::UnregisterWinRTObject
helpviewer_keywords:
- Microsoft::WRL::Module class
- Microsoft::WRL::Module::Create method
- Microsoft::WRL::Module::DecrementObjectCount method
- Microsoft::WRL::Module::GetActivationFactory method
- Microsoft::WRL::Module::GetClassObject method
- Microsoft::WRL::Module::GetModule method
- Microsoft::WRL::Module::GetObjectCount method
- Microsoft::WRL::Module::IncrementObjectCount method
- Microsoft::WRL::Module::Module, constructor
- Microsoft::WRL::Module::objectCount_ data member
- Microsoft::WRL::Module::RegisterCOMObject method
- Microsoft::WRL::Module::RegisterObjects method
- Microsoft::WRL::Module::RegisterWinRTObject method
- Microsoft::WRL::Module::releaseNotifier_ data member
- Microsoft::WRL::Module::Terminate method
- Microsoft::WRL::Module::~Module, destructor
- Microsoft::WRL::Module::UnregisterCOMObject method
- Microsoft::WRL::Module::UnregisterObjects method
- Microsoft::WRL::Module::UnregisterWinRTObject method
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
ms.openlocfilehash: f7930247c979c111a7f4798e35ebe7aa95209f37
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225754"
---
# <a name="module-class"></a>Modül Sınıfı

İlgili nesneler koleksiyonunu temsil eder.

## <a name="syntax"></a>Söz dizimi

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>Parametreler

*moduleType*<br/>
Bir veya daha fazla [ModuleType](moduletype-enumeration.md) numaralandırma değerinin birleşimi.

## <a name="members"></a>Üyeler

### <a name="protected-classes"></a>Korumalı sınıflar

Ad                                                                                | Açıklama
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier](module-genericreleasenotifier-class.md) | Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi, bir lambda, functor veya işlev işaretçisi üzerinde tarafından belirtilir.
[Module:: MethodReleaseNotifier](module-methodreleasenotifier-class.md)   | Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi bir nesne ve onun işaretçiden yönteme üyesi tarafından belirtilir.
[Module:: ReleaseNotifier](module-releasenotifier-class.md)               | Bir modüldeki son nesne bırakıldığında bir olay işleyicisini çağırır.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                             | Açıklama
-------------------------------- | -----------------------------------------------------------
[Module:: ~ modül](#tilde-module) | Sınıfın geçerli örneğini kaldırır `Module` .

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Ad                      | Açıklama
------------------------- | ---------------------------------------------------
[Module:: Module](#module) | `Module` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                    | Açıklama
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Module:: Create](#create)                               | Bir modül örneği oluşturur.
[Modül::D ecrementObjectCount](#decrementobjectcount)   | Modül tarafından izlenen nesne sayısını azaltır.
[Module:: GetActivationFactory](#getactivationfactory)   | Modül için bir etkinleştirme fabrikası alır.
[Module:: GetClassObject](#getclassobject)               | Sınıf fabrikalarının bir önbelleğini alır.
[Module:: GetModule](#getmodule)                         | Bir modül örneği oluşturur.
[Module:: GetObjectCount](#getobjectcount)               | Bu modülle yönetilen nesne sayısını alır.
[Module:: IncrementObjectCount](#incrementobjectcount)   | Modül tarafından izlenen nesne sayısını artırır.
[Module:: RegisterCOMObject](#registercomobject)         | Bir veya daha fazla COM nesnesini kaydeder, böylece diğer uygulamalar bunlara bağlanabilir.
[Module:: RegisterObjects](#registerobjects)             | Diğer uygulamaların bağlanabilmesi için COM veya Windows Çalışma Zamanı nesnelerini kaydettirir.
[Module:: RegisterWinRTObject](#registerwinrtobject)     | Bir veya daha fazla Windows Çalışma Zamanı nesnesini kaydeder, böylece diğer uygulamalar bunlara bağlanabilir.
[Module:: Terminate](#terminate)                         | Modül tarafından başlatılan tüm fabrikaların kapatılmasını sağlar.
[Module:: UnregisterCOMObject](#unregistercomobject)     | Bir veya daha fazla COM nesnesinin kaydını siler, bu, diğer uygulamaların bunlara bağlanmasını engeller.
[Module:: UnregisterObjects](#unregisterobjects)         | Diğer uygulamaların bunlara bağlanabilmesi için belirtilen modüldeki nesnelerin kaydını siler.
[Module:: UnregisterWinRTObject](#unregisterwinrtobject) | Diğer uygulamaların bunlara bağlanamamasını sağlamak için bir veya daha fazla Windows Çalışma Zamanı nesnesinin kaydını siler.

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                      | Açıklama
------------------------- | --------------------------------
[Module:: Create](#create) | Bir modül örneği oluşturur.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                         | Açıklama
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Modül:: objectCount_](#objectcount)         | [Make](make-function.md) işleviyle birlikte kaç sınıf oluşturulduğunu izler.
[Modül:: releaseNotifier_](#releasenotifier) | Bir nesne için bir işaretçi tutar `ReleaseNotifier` .

### <a name="macros"></a>Makrolar

Ad                                                                   | Açıklama
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ActivatableClass](activatableclass-macros.md)              | Belirtilen sınıfın bir örneğini oluşturabileceğiniz bir fabrika içeren bir iç önbelleği doldurur. Bu makro varsayılan fabrika ve Grup KIMLIĞI parametrelerini belirtir.
[ActivatableClassWithFactory](activatableclass-macros.md)   | Belirtilen sınıfın bir örneğini oluşturabileceğiniz bir fabrika içeren bir iç önbelleği doldurur. Bu makro belirli bir fabrika parametresi belirtmenize olanak sağlar.
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | Belirtilen sınıfın bir örneğini oluşturabileceğiniz bir fabrika içeren bir iç önbelleği doldurur. Bu makro, belirli fabrika ve Grup KIMLIĞI parametrelerini belirtmenize olanak sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="modulemodule"></a><a name="tilde-module"></a>Module:: ~ modül

Sınıfın geçerli örneğini kaldırır `Module` .

```cpp
virtual ~Module();
```

## <a name="modulecreate"></a><a name="create"></a>Module:: Create

Bir modül örneği oluşturur.

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Modül türü.

*callback*<br/>
Modülün son örnek nesnesi serbest bırakıldığında çağırılır.

*object*<br/>
*Nesne* ve *Yöntem* parametreleri birlikte kullanılır. Modüldeki son örnek nesnesi bırakıldığında son örnek nesnesine işaret eder.

*yöntemidir*<br/>
*Nesne* ve *Yöntem* parametreleri birlikte kullanılır. Modüldeki son örnek nesnesi bırakıldığında son örnek nesnesinin yöntemine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Modüle başvuru.

## <a name="moduledecrementobjectcount"></a><a name="decrementobjectcount"></a>Modül::D ecrementObjectCount

Modül tarafından izlenen nesne sayısını azaltır.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Dönüş Değeri

Azaltma işleminden önceki sayı.

## <a name="modulegetactivationfactory"></a><a name="getactivationfactory"></a>Module:: GetActivationFactory

Modül için bir etkinleştirme fabrikası alır.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*pActivatibleClassId*<br/>
Çalışma zamanı sınıfının IID 'si.

*ppIFactory*<br/>
Belirtilen çalışma zamanı sınıfı için IActivationFactory.

*serverName*<br/>
Geçerli modüldeki sınıf fabrikalarının bir alt kümesinin adı. [ActivatableClassWithFactoryEx](activatableclass-macros.md) makrosunda kullanılan sunucu adını belirtin veya **`nullptr`** varsayılan sunucu adını almak için öğesini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi halde, GetActivationFactory tarafından döndürülen HRESULT.

## <a name="modulegetclassobject"></a><a name="getclassobject"></a>Module:: GetClassObject

Kuyruklarının bir sınıf fabrikası önbelleği.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Sınıf KIMLIĞI.

*riıd*<br/>
İsteğiniz arabirim KIMLIĞI.

*PPV*<br/>
Döndürülen nesneye yönelik işaretçi.

*serverName*<br/>
Sunucu adı, `ActivatableClassWithFactory` `ActivatableClassWithFactoryEx` , veya makroda ya da `ActivatableClass` **`nullptr`** varsayılan sunucu adını almak için.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca COM için kullanın, Windows Çalışma Zamanı değil. Bu yöntem yalnızca `IClassFactory` yöntemleri gösterir.

## <a name="modulegetmodule"></a><a name="getmodule"></a>Module:: GetModule

Bir modül örneği oluşturur.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Dönüş Değeri

Bir modüle başvuru.

## <a name="modulegetobjectcount"></a><a name="getobjectcount"></a>Module:: GetObjectCount

Bu modülle yönetilen nesne sayısını alır.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu modül tarafından yönetilen geçerli nesne sayısı.

## <a name="moduleincrementobjectcount"></a><a name="incrementobjectcount"></a>Module:: IncrementObjectCount

Modül tarafından izlenen nesne sayısını artırır.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Dönüş Değeri

Artış işleminden önceki sayı.

## <a name="modulemodule"></a><a name="module"></a>Module:: Module

`Module` sınıfının yeni bir örneğini başlatır.

```cpp
Module();
```

### <a name="remarks"></a>Açıklamalar

Bu Oluşturucu korunuyor ve **`new`** anahtar sözcüğüyle çağrılamaz. Bunun yerine, [Module:: GetModule](#getmodule) ya da [Module:: Create](#create)' ı çağırın.

## <a name="moduleobjectcount_"></a><a name="objectcount"></a>Modül:: objectCount_

[Make](make-function.md) işleviyle birlikte kaç sınıf oluşturulduğunu izler.

```cpp
volatile long objectCount_;
```

## <a name="moduleregistercomobject"></a><a name="registercomobject"></a>Module:: RegisterCOMObject

Bir veya daha fazla COM nesnesini kaydeder, böylece diğer uygulamalar bunlara bağlanabilir.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>Parametreler

*serverName*<br/>
Bir sunucunun tam adı.

*'leri*<br/>
Kaydolmak için bir CLSID dizisi.

*larının*<br/>
Kullanılabilirliği yayımlanmakta olan sınıf nesnelerinin IUnknown arabirimleri dizisi.

*özgü*<br/>
İşlem tamamlandığında, kayıtlı sınıf nesnelerini tanımlayan değerlere yönelik işaretçilerin bir dizisi. Bu değerler daha sonra kaydı iptal etmek için kullanılır.

*biriktirme*<br/>
Kaydolmak için CLSID sayısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa Aksi takdirde, işlemin başarısız olma nedenini belirten CO_E_OBJISREG gibi bir HRESULT.

### <a name="remarks"></a>Açıklamalar

COM nesneleri CLSCTX numaralandırmasının CLSCTX_LOCAL_SERVER numaralandırıcısı ile kaydedilir.

Kayıtlı nesnelerle bağlantı türü, geçerli *comflag* Template parametresinin bir BIRLEŞIMI ve regcls numaralandırması regcls_suspended numaralandırıcısı ile belirtilir.

## <a name="moduleregisterobjects"></a><a name="registerobjects"></a>Module:: RegisterObjects

Diğer uygulamaların bağlanabilmesi için COM veya Windows Çalışma Zamanı nesnelerini kaydettirir.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parametreler

*birimi*<br/>
COM veya Windows Çalışma Zamanı nesneleri dizisi.

*serverName*<br/>
Nesneleri oluşturan sunucunun adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, işlemin başarısız olma nedenini gösteren bir HRESULT.

## <a name="moduleregisterwinrtobject"></a><a name="registerwinrtobject"></a>Module:: RegisterWinRTObject

Bir veya daha fazla Windows Çalışma Zamanı nesnesini kaydeder, böylece diğer uygulamalar bunlara bağlanabilir.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>Parametreler

*serverName*<br/>
Bu işlemden etkilenen nesnelerin bir alt kümesini belirten ad.

*activatableClassIds*<br/>
Kaydolmak için bir etkinleştirilebilir CLSID dizisi.

*bilgilerinin*<br/>
Kayıtlı olan sınıf nesnelerini tanımlayan bir değer. Bu değer daha sonra kaydı iptal etmek için kullanılır.

*biriktirme*<br/>
Kaydedileceği nesne sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, işlemin başarısız olma nedenini belirten CO_E_OBJISREG gibi bir hata HRESULT.

## <a name="modulereleasenotifier_"></a><a name="releasenotifier"></a>Modül:: releaseNotifier_

Bir nesne için bir işaretçi tutar `ReleaseNotifier` .

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="moduleterminate"></a><a name="terminate"></a>Module:: Terminate

Modül tarafından başlatılan tüm fabrikaların kapatılmasını sağlar.

```cpp
void Terminate();
```

### <a name="remarks"></a>Açıklamalar

Önbellekteki fabrikaları serbest bırakır.

## <a name="moduleunregistercomobject"></a><a name="unregistercomobject"></a>Module:: UnregisterCOMObject

Bir veya daha fazla COM nesnesinin kaydını siler, bu, diğer uygulamaların bunlara bağlanmasını engeller.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Parametreler

*serverName*<br/>
Kullanılmayan

*özgü*<br/>
Kayıt kaldırılacak sınıf nesnelerini tanımlayan değerlere işaretçiler dizisi. Dizi [RegisterCOMObject](#registercomobject) yöntemi tarafından oluşturuldu.

*biriktirme*<br/>
Kayıt için kullanılacak sınıfların sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; Aksi takdirde, işlemin başarısız olma nedenini gösteren HRESULT hatası.

## <a name="moduleunregisterobjects"></a><a name="unregisterobjects"></a>Module:: UnregisterObjects

Diğer uygulamaların bunlara bağlanabilmesi için belirtilen modüldeki nesnelerin kaydını siler.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parametreler

*birimi*<br/>
Modül işaretçisi.

*serverName*<br/>
Bu işlemden etkilenen nesnelerin bir alt kümesini belirten uygun bir ad.

### <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; Aksi takdirde, bu işlemin başarısız olmasının nedenini belirten bir HRESULT hatası.

## <a name="moduleunregisterwinrtobject"></a><a name="unregisterwinrtobject"></a>Module:: UnregisterWinRTObject

Diğer uygulamaların bunlara bağlanamamasını sağlamak için bir veya daha fazla Windows Çalışma Zamanı nesnesinin kaydını siler.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Parametreler

*bilgilerinin*<br/>
Kaydı iptal edilecek olan sınıf nesnesini tanımlayan bir değere yönelik işaretçi.
