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
ms.openlocfilehash: db3eb123382ac70f6198d094c5eb3fe44d3bbcd9
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335195"
---
# <a name="module-class"></a>Modül Sınıfı

İlgili nesneler koleksiyonunu temsil eder.

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

*moduleType*<br/>
Bir veya daha fazla birleşimi [ModuleType](moduletype-enumeration.md) sabit listesi değerleri.

## <a name="members"></a>Üyeler

### <a name="protected-classes"></a>Korumalı sınıflar

Ad                                                                                | Açıklama
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier](module-genericreleasenotifier-class.md) | Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyici lambda, functor veya işaretçi işlevi tarafından belirtilir.
[Module::MethodReleaseNotifier](module-methodreleasenotifier-class.md)   | Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyicisi, bir nesne ve onun yöntemi için işaretçi üye tarafından belirtilir.
[Module::ReleaseNotifier](module-releasenotifier-class.md)               | Modül içindeki son nesnenin yayımlandığında bir olay işleyici çağırır.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                             | Açıklama
-------------------------------- | -----------------------------------------------------------
[Modül:: ~ Modülü](#tilde-module) | Geçerli örneğinin başlatmasını geri alır `Module` sınıfı.

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Ad                      | Açıklama
------------------------- | ---------------------------------------------------
[Module::Module](#module) | Yeni bir örneğini başlatır `Module` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                    | Açıklama
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Module::Create](#create)                               | Bir modülün örneği oluşturur.
[Module::DecrementObjectCount](#decrementobjectcount)   | Nesne sayısını modülü tarafından izlenen azaltır.
[Module::GetActivationFactory](#getactivationfactory)   | Etkinleştirme fabrikası için modülü alır.
[Module::GetClassObject](#getclassobject)               | Sınıf üreteçlerini önbelleğini alır.
[Module::GetModule](#getmodule)                         | Bir modülün örneği oluşturur.
[Module::GetObjectCount](#getobjectcount)               | Bu modülü tarafından yönetilen nesne sayısını alır.
[Module::ıncrementobjectcount](#incrementobjectcount)   | Modül tarafından izlenen nesne sayısını artırır.
[Module::RegisterCOMObject](#registercomobject)         | Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.
[Module::RegisterObjects](#registerobjects)             | Diğer uygulamalar için bağlanabilmesi için COM veya Windows çalışma zamanı nesneleri kaydeder.
[Module::RegisterWinRTObject](#registerwinrtobject)     | Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla Windows çalışma zamanı nesneleri kaydeder.
[Module::Terminate](#terminate)                         | Kapatmak için modülü tarafından oluşturulan tüm fabrikaları neden olur.
[Module::UnregisterCOMObject](#unregistercomobject)     | Bir veya daha fazla COM nesneleri, diğer uygulamalar için bağlanmasını engelleyen kaydını siler.
[Module::UnregisterObjects](#unregisterobjects)         | Diğer uygulamalar için bağlantı nesneleri belirtilen modüldeki kaydını siler.
[Module::UnregisterWinRTObject](#unregisterwinrtobject) | Böylece diğer uygulamalar için bağlanılamıyor veya daha fazla Windows çalışma zamanı nesne kaydını siler.

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                      | Açıklama
------------------------- | --------------------------------
[Module::Create](#create) | Bir modülün örneği oluşturur.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                         | Açıklama
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Module::objectCount_](#objectcount)         | Kaç tane sınıfları ile oluşturulmuş izler [olun](make-function.md) işlevi.
[Module::releaseNotifier_](#releasenotifier) | Bir işaretçi tutan bir `ReleaseNotifier` nesne.

### <a name="macros"></a>Makrolar

Ad | Açıklama------| --- [ActivatableClass](activatableclass-macros.md) |  Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur. Bu makro, varsayılan fabrika ve grup kimliği parametreleri belirtir.
[ActivatableClassWithFactory](activatableclass-macros.md) | Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur. Bu makro belirli Fabrika parametresi belirlemenize olanak sağlar.
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur. Bu makro belirli Fabrika ve grup kimliği parametreleri belirtmenizi sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="tilde-module"></a>Modül:: ~ Modülü

Geçerli örneğinin başlatmasını geri alır `Module` sınıfı.

```cpp
virtual ~Module();
```

## <a name="create"></a>Module::Create

Bir modülün örneği oluşturur.

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

*geri çağırma*<br/>
Son örnek nesnesi modülünün bırakıldığında çağırılır.

*object*<br/>
*Nesne* ve *yöntemi* parametreleri birlikte kullanılır. Son örnek nesne modülünde yayımlandığında son örnek nesnesi işaret eder.

*Yöntemi*<br/>
*Nesne* ve *yöntemi* parametreleri birlikte kullanılır. Nesnenin son örnek nesne modülünde yayımlandığında son örneği noktaları yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Modül başvuru.

## <a name="decrementobjectcount"></a>Module::DecrementObjectCount

Nesne sayısını modülü tarafından izlenen azaltır.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Dönüş Değeri

Azaltma işleminden önce sayısı.

## <a name="getactivationfactory"></a>Module::GetActivationFactory

Etkinleştirme fabrikası için modülü alır.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*pActivatibleClassId*<br/>
Laboratuvardaki bir çalışma zamanı sınıf.

*ppIFactory*<br/>
Belirtilen çalışma zamanı sınıfının IActivationFactory.

*SunucuAdı*<br/>
Sınıf üreteçlerini geçerli modüldeki bir alt kümesi adı. Kullanılan sunucu adını belirtmek [ActivatableClassWithFactoryEx](activatableclass-macros.md) makro veya belirtin `nullptr` varsayılan sunucu adı alınamıyor.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde GetActivationFactory tarafından döndürülen HRESULT.

## <a name="getclassobject"></a>Module::GetClassObject

Sınıf üreteçlerini önbelleğini Retreives.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
Sınıf kimliği

*riid*<br/>
İstek, arabirim kimliği.

*ppv*<br/>
Döndürülen nesne işaretçisi.

*SunucuAdı*<br/>
Ya da belirtilen sunucu adı `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, veya `ActivatableClass` makrosu; veya `nullptr` varsayılan sunucu adı alınamıyor.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Yalnızca COM için değil Windows çalışma zamanı bu yöntemi kullanın. Bu yöntem yalnızca sunan `IClassFactory` yöntemleri.

## <a name="getmodule"></a>Module::GetModule

Bir modülün örneği oluşturur.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Dönüş Değeri

Modül başvuru.

## <a name="getobjectcount"></a>Module::GetObjectCount

Bu modülü tarafından yönetilen nesne sayısını alır.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu modülü tarafından yönetilen nesnelere geçerli sayısı.

## <a name="incrementobjectcount"></a>Module::ıncrementobjectcount

Modül tarafından izlenen nesne sayısını artırır.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Dönüş Değeri

Önce Artım işlemi sayısı.

## <a name="module"></a>Module::Module

Yeni bir örneğini başlatır `Module` sınıfı.

```cpp
Module();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu korunur ve ile çağrılamaz `new` anahtar sözcüğü. Bunun yerine, ya da çağrı [Module::GetModule](#getmodule) veya [Module::Create](#create).

## <a name="objectcount"></a>Module::objectCount_

Kaç tane sınıfları ile oluşturulmuş izler [olun](make-function.md) işlevi.

```cpp
volatile long objectCount_;
```

## <a name="registercomobject"></a>Module::RegisterCOMObject

Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>Parametreler

*SunucuAdı*<br/>
Bir sunucunun tam adı.

*CLSID*<br/>
CLSID kaydetmek için bir dizi.

*fabrikaları*<br/>
IUnknown arabirimi olan kullanılabilirlik yayımlanan sınıf nesnelerinin dizisi.

*Tanımlama bilgileri*<br/>
İşlem tamamlandığında, kayıtlı olan bir sınıfı değerleri için işaretçiler dizisi nesneleri. Bu değerler daha sonra kullanılır kaydını iptal etme.

*Sayısı*<br/>
Kaydedilecek CLSID sayısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK varsa saldırgan; Aksi takdirde, bir HRESULT nedenini belirten CO_E_OBJISREG gibi işlem başarısız oldu.

### <a name="remarks"></a>Açıklamalar

COM nesnelerinin CLSCTX numaralandırma CLSCTX_LOCAL_SERVER Numaralandırıcı ile kaydedilir.

Kayıtlı nesneler için bağlantı türü, geçerli bir birleşimi tarafından belirtilen *comflag* şablon parametresi ile REGCLS numaralandırma REGCLS_SUSPENDED Numaralandırıcı.

## <a name="registerobjects"></a>Module::RegisterObjects

Diğer uygulamalar için bağlanabilmesi için COM veya Windows çalışma zamanı nesneleri kaydeder.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parametreler

*module*<br/>
COM veya Windows çalışma zamanı nesneleri dizisi.

*SunucuAdı*<br/>
Nesneleri oluşturan sunucunun adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, nedenini belirten bir HRESULT, işlem başarısız oldu.

## <a name="registerwinrtobject"></a>Module::RegisterWinRTObject

Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla Windows çalışma zamanı nesneleri kaydeder.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>Parametreler

*SunucuAdı*<br/>
Bu işlemden etkilenen nesneler kümesini belirten bir ad.

*activatableClassIds*<br/>
Kaydedilecek etkinleştirilebilir CLSID dizisi.

*Tanımlama bilgisi*<br/>
Kaydedilen sınıf nesneleri tanımlayan bir değer. Bu değer daha sonra kaydı iptal etmek için kullanılır.

*Sayısı*<br/>
Kaydedilecek nesne sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde bir hata HRESULT nedenini belirten CO_E_OBJISREG gibi işlem başarısız oldu.

## <a name="releasenotifier"></a>Module::releaseNotifier_

Bir işaretçi tutan bir `ReleaseNotifier` nesne.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="terminate"></a>Module::Terminate

Kapatmak için modülü tarafından oluşturulan tüm fabrikaları neden olur.

```cpp
void Terminate();
```

### <a name="remarks"></a>Açıklamalar

Önbellek Fabrikalar serbest bırakır.

## <a name="unregistercomobject"></a>Module::UnregisterCOMObject

Bir veya daha fazla COM nesneleri, diğer uygulamalar için bağlanmasını engelleyen kaydını siler.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Parametreler

*SunucuAdı*<br/>
(Kullanılmayan)

*Tanımlama bilgileri*<br/>
Sınıf nesneleri silinmesine izin değerleri için işaretçiler dizisi. Dizi tarafından oluşturulan [RegisterCOMObject](#registercomobject) yöntemi.

*Sayısı*<br/>
Sınıfların kaydını sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; Aksi takdirde bir hata nedenini belirten HRESULT işlemi başarısız oldu.

## <a name="unregisterobjects"></a>Module::UnregisterObjects

Diğer uygulamalar için bağlantı nesneleri belirtilen modüldeki kaydını siler.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parametreler

*module*<br/>
Bir modül için işaretçi.

*SunucuAdı*<br/>
Bu işlemden etkilenen nesneler kümesini belirtir uygun bir ad.

### <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; Aksi takdirde bir hata nedenini belirten HRESULT bu işlemi başarısız oldu.

## <a name="unregisterwinrtobject"></a>Module::UnregisterWinRTObject

Böylece diğer uygulamalar için bağlanılamıyor veya daha fazla Windows çalışma zamanı nesne kaydını siler.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Parametreler

*Tanımlama bilgisi*<br/>
Kaydını iptal edilmesine izin sınıfı nesne tanımlayan bir değer için bir işaretçi.
