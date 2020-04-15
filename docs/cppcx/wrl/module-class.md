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
ms.openlocfilehash: afd2edacefdf5d62b50a03c0a8c37f13ee5d9c9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371313"
---
# <a name="module-class"></a>Modül Sınıfı

İlişkili nesnelerin bir koleksiyonunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>Parametreler

*modülTipi*<br/>
Bir veya daha fazla [ModuleType](moduletype-enumeration.md) numaralandırma değerlerinin birleşimi.

## <a name="members"></a>Üyeler

### <a name="protected-classes"></a>Korumalı Sınıflar

Adı                                                                                | Açıklama
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Modül::GenericReleaseNotifier](module-genericreleasenotifier-class.md) | Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisi çağırır. Olay işleyicisi bir lambda, functor veya işaretçi-to-fonksiyon tarafından belirtilir.
[Modül::MethodReleaseNotifier](module-methodreleasenotifier-class.md)   | Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisi çağırır. Olay işleyicisi bir nesne ve onun işaretçi-to-a-method üyesi tarafından belirtilir.
[Modül::ReleaseNotifier](module-releasenotifier-class.md)               | Modüldeki son nesne serbest bırakıldığında bir olay işleyicisi çağırır.

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                             | Açıklama
-------------------------------- | -----------------------------------------------------------
[Modül::~Modül](#tilde-module) | Sınıfın geçerli örneğini `Module` deinitialize eder.

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Adı                      | Açıklama
------------------------- | ---------------------------------------------------
[Modül::Modül](#module) | `Module` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                    | Açıklama
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Modül::Oluştur](#create)                               | Bir modül örneği oluşturur.
[Modül::DecrementObjectCount](#decrementobjectcount)   | Modül tarafından izlenen nesne sayısını eriter.
[Modül::GetActivationFactory](#getactivationfactory)   | Modül için bir aktivasyon fabrikası alır.
[Modül::GetClassObject](#getclassobject)               | Sınıf fabrikalarının önbelleğini alır.
[Modül::GetModule](#getmodule)                         | Bir modül örneği oluşturur.
[Modül::GetObjectCount](#getobjectcount)               | Bu modül tarafından yönetilen nesne sayısını alır.
[Modül::ArtışNesne Sayısı](#incrementobjectcount)   | Modül tarafından izlenen nesne sayısını artımlar.
[Modül::RegisterCOMObject](#registercomobject)         | Diğer uygulamaların bunlara bağlanabilmesi için bir veya daha fazla COM nesnesini kaydeder.
[Modül::RegisterObjects](#registerobjects)             | Diğer uygulamaların bunlara bağlanabilmesi için COM veya Windows Runtime nesnelerini kaydeder.
[Modül:RegisterWinRTObject](#registerwinrtobject)     | Diğer uygulamaların bunlara bağlanabilmesi için bir veya daha fazla Windows Runtime nesnesini kaydeder.
[Modül::Sonlandırma](#terminate)                         | Modül tarafından anında kapatılan tüm fabrikaların kapanmasına neden olur.
[Modül::UnregisterCOMObject](#unregistercomobject)     | Diğer uygulamaların bunlara bağlanmasını engelleyen bir veya daha fazla COM nesnesini kaydeder.
[Modül::Kayıt Dışı Nesneler](#unregisterobjects)         | Diğer uygulamaların bunlara bağlanamaması için belirtilen modüldeki nesneleri kaydeder.
[Modül::Kayıt DışıWinRTObject](#unregisterwinrtobject) | Diğer uygulamaların bunlara bağlanamaması için bir veya daha fazla Windows Runtime nesnesini unregisters.

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                      | Açıklama
------------------------- | --------------------------------
[Modül::Oluştur](#create) | Bir modül örneği oluşturur.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                                         | Açıklama
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Modül:objectCount_](#objectcount)         | [Yap](make-function.md) işlevi yle kaç sınıf oluşturulduğunu izler.
[Modül:releaseNotifier_](#releasenotifier) | Bir `ReleaseNotifier` nesneye işaretçi tutar.

### <a name="macros"></a>Makrolar

Adı                                                                   | Açıklama
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ActivatableSınıf](activatableclass-macros.md)              | Belirtilen sınıfın bir örneğini oluşturabilecek bir fabrika içeren bir iç önbelleği doldurur. Bu makro varsayılan fabrika ve grup kimliği parametrelerini belirtir.
[ActivatableClassWithFactory](activatableclass-macros.md)   | Belirtilen sınıfın bir örneğini oluşturabilecek bir fabrika içeren bir iç önbelleği doldurur. Bu makro, belirli bir fabrika parametresi belirtmenizi sağlar.
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | Belirtilen sınıfın bir örneğini oluşturabilecek bir fabrika içeren bir iç önbelleği doldurur. Bu makro, belirli fabrika ve grup kimliği parametrelerini belirtmenizi sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="modulemodule"></a><a name="tilde-module"></a>Modül::~Modül

Sınıfın geçerli örneğini `Module` deinitialize eder.

```cpp
virtual ~Module();
```

## <a name="modulecreate"></a><a name="create"></a>Modül::Oluştur

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

*Geri*<br/>
Modülün son örnek nesnesi serbest bırakıldığında çağrılır.

*Nesne*<br/>
*Nesne* ve *yöntem* parametreleri birlikte kullanılır. Modüldeki son örnek nesne solduğunda son örnek nesneyi işaret edin.

*Yöntem*<br/>
*Nesne* ve *yöntem* parametreleri birlikte kullanılır. Modüldeki son örnek nesne solduğunda son örnek nesnenin yöntemine işaret edilir.

### <a name="return-value"></a>Dönüş Değeri

Modüle başvuru.

## <a name="moduledecrementobjectcount"></a><a name="decrementobjectcount"></a>Modül::DecrementObjectCount

Modül tarafından izlenen nesne sayısını eriter.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Dönüş Değeri

Kararname işleminden önceki sayım.

## <a name="modulegetactivationfactory"></a><a name="getactivationfactory"></a>Modül::GetActivationFactory

Modül için bir aktivasyon fabrikası alır.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*pActivatibleClassId*<br/>
Çalışma zamanı sınıfının IID'si.

*ppIFactory*<br/>
Belirtilen çalışma zamanı sınıfı için IActivationFactory.

*Sunucuadı*<br/>
Geçerli modüldeki sınıf fabrikalarının bir alt kümesinin adı. [ActivatableClassWithFactoryEx](activatableclass-macros.md) makroda kullanılan sunucu adını belirtin veya varsayılan sunucu adını almak için belirtin. `nullptr`

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, HRESULT GetActivationFactory tarafından döndürülür.

## <a name="modulegetclassobject"></a><a name="getclassobject"></a>Modül::GetClassObject

Sınıf fabrikalarının önbelleğini retreives.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Sınıf kimliği.

*Riid*<br/>
İstediğinin arayüz kimliği.

*Ppv*<br/>
Döndürülen nesneye işaretçi.

*Sunucuadı*<br/>
`ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`veya `ActivatableClass` makroda belirtilen sunucu adı; veya `nullptr` varsayılan sunucu adını almak için.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu yöntemi Yalnızca COM için kullanın, Windows Runtime için değil. Bu yöntem yalnızca `IClassFactory` yöntemleri ortaya çıkarır.

## <a name="modulegetmodule"></a><a name="getmodule"></a>Modül::GetModule

Bir modül örneği oluşturur.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Dönüş Değeri

Bir modüle başvuru.

## <a name="modulegetobjectcount"></a><a name="getobjectcount"></a>Modül::GetObjectCount

Bu modül tarafından yönetilen nesne sayısını alır.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu modül tarafından yönetilen nesnelerin geçerli sayısı.

## <a name="moduleincrementobjectcount"></a><a name="incrementobjectcount"></a>Modül::ArtışNesne Sayısı

Modül tarafından izlenen nesne sayısını artımlar.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Dönüş Değeri

Artış işleminden önceki sayım.

## <a name="modulemodule"></a><a name="module"></a>Modül::Modül

`Module` sınıfının yeni bir örneğini başlatır.

```cpp
Module();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu korunur ve `new` anahtar kelime ile çağrılamaz. Bunun yerine, [Modül::GetModule](#getmodule) veya [Modül::Oluştur'](#create)u arayın.

## <a name="moduleobjectcount_"></a><a name="objectcount"></a>Modül:objectCount_

[Yap](make-function.md) işlevi yle kaç sınıf oluşturulduğunu izler.

```cpp
volatile long objectCount_;
```

## <a name="moduleregistercomobject"></a><a name="registercomobject"></a>Modül::RegisterCOMObject

Diğer uygulamaların bunlara bağlanabilmesi için bir veya daha fazla COM nesnesini kaydeder.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>Parametreler

*Sunucuadı*<br/>
Bir sunucunun tam nitelikli adı.

*Clsıd*<br/>
Kaydolmak için bir dizi CLSID.

*Fabrika*<br/>
Kullanılabilirliği yayımlanmakta olan sınıf nesnelerinin Bilinmeyen arabirimleri dizisi.

*Kurabiye*<br/>
İşlem tamamlandığında, sınıf nesneleri tanımlanan değerlere işaretçiler dizisi kaydedilir. Bu değerler daha sonra kaydı iptal etmek için kullanılır.

*Sayısı*<br/>
Kaydolunacak CLSID sayısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK eğer successfu; aksi takdirde, işlemin başarısız olmasının nedenini gösteren CO_E_OBJISREG gibi bir HRESULT olur.

### <a name="remarks"></a>Açıklamalar

COM nesneleri CLSCTX numaralandırmaCLSCTX_LOCAL_SERVER numaralandırması ile kaydedilir.

Kayıtlı nesnelere bağlantı türü, geçerli *comflag* şablon parametresi ve REGCLS numaralandırmasının REGCLS_SUSPENDED numaralandırmasının birleşimi ile belirtilir.

## <a name="moduleregisterobjects"></a><a name="registerobjects"></a>Modül::RegisterObjects

Diğer uygulamaların bunlara bağlanabilmesi için COM veya Windows Runtime nesnelerini kaydeder.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parametreler

*Modülü*<br/>
Bir dizi COM veya Windows Runtime nesnesi.

*Sunucuadı*<br/>
Nesneleri oluşturan sunucunun adı.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, işlemin başarısız olmasının nedenini gösteren bir HRESULT olur.

## <a name="moduleregisterwinrtobject"></a><a name="registerwinrtobject"></a>Modül:RegisterWinRTObject

Diğer uygulamaların bunlara bağlanabilmesi için bir veya daha fazla Windows Runtime nesnesini kaydeder.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>Parametreler

*Sunucuadı*<br/>
Bu işlemden etkilenen nesnelerin bir alt kümesini belirten bir ad.

*activatableClassIds*<br/>
Kaydolmak için etkinleştirilebilir CLSIDs bir dizi.

*Çerez*<br/>
Kayıtlı sınıf nesnelerini tanımlayan bir değer. Bu değer daha sonra kaydı iptal etmek için kullanılır.

*Sayısı*<br/>
Kaydolunacak nesne sayısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, işlemin başarısız olmasının nedenini gösteren CO_E_OBJISREG gibi bir hata HRESULT olur.

## <a name="modulereleasenotifier_"></a><a name="releasenotifier"></a>Modül:releaseNotifier_

Bir `ReleaseNotifier` nesneye işaretçi tutar.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="moduleterminate"></a><a name="terminate"></a>Modül::Sonlandırma

Modül tarafından anında kapatılan tüm fabrikaların kapanmasına neden olur.

```cpp
void Terminate();
```

### <a name="remarks"></a>Açıklamalar

Önbellekteki fabrikaları serbest bırakır.

## <a name="moduleunregistercomobject"></a><a name="unregistercomobject"></a>Modül::UnregisterCOMObject

Diğer uygulamaların bunlara bağlanmasını engelleyen bir veya daha fazla COM nesnesini kaydeder.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Parametreler

*Sunucuadı*<br/>
(Kullanılmayan)

*Kurabiye*<br/>
Sınıf nesnelerinin kaydedilmemiş olmasını tanımlayan değerlere işaretçiler dizisi. Dizi [RegisterCOMObject](#registercomobject) yöntemi tarafından oluşturuldu.

*Sayısı*<br/>
Kayıt tanıtırılacak sınır sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; aksi takdirde, işlemin başarısız olmasının nedenini gösteren bir hata HRESULT olur.

## <a name="moduleunregisterobjects"></a><a name="unregisterobjects"></a>Modül::Kayıt Dışı Nesneler

Diğer uygulamaların bunlara bağlanamaması için belirtilen modüldeki nesneleri kaydeder.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parametreler

*Modülü*<br/>
Bir modüliçin işaretçi.

*Sunucuadı*<br/>
Bu işlemden etkilenen nesnelerin bir alt kümesini belirten nitelikli bir ad.

### <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; aksi takdirde, bu işlemin başarısız olmasının nedenini gösteren bir hata HRESULT olur.

## <a name="moduleunregisterwinrtobject"></a><a name="unregisterwinrtobject"></a>Modül::Kayıt DışıWinRTObject

Diğer uygulamaların bunlara bağlanamaması için bir veya daha fazla Windows Runtime nesnesini unregisters.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Parametreler

*Çerez*<br/>
Kaydı iptal edilecek sınıf nesnesini tanımlayan bir değeriçin işaretçi.
