---
title: WeakRef sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f40e0509f5e532ea85930052a6bda35d89e47ae1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071030"
---
# <a name="weakref-class"></a>WeakRef Sınıfı

Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::WeakRef Oluşturucusu](#weakref)|Yeni bir örneğini başlatır `WeakRef` sınıfı.|
|[WeakRef::~WeakRef Yıkıcısı](#tilde-weakref)|Geçerli örneğinin başlatmasını geri alır `WeakRef` sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::As Metodu](#as)|Belirtilen ayarlar `ComPtr` belirtilen arabirim temsil etmek için işaretçi parametresi.|
|[WeakRef::AsIID Metodu](#asiid)|Belirtilen ayarlar `ComPtr` belirtilen arabirim kimliği. temsil etmek için işaretçi parametresi|
|[WeakRef::CopyTo Metodu](#copyto)|Bir işaretçi bir arabirim için kullanılabiliyorsa, belirtilen bir işaretçi değişkenine atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::operator& İşleci](#operator-ampersand-operator)|Döndürür bir `ComPtrRef` geçerli temsil eden nesne `WeakRef` nesne.|

## <a name="remarks"></a>Açıklamalar

A `WeakRef` nesne tutan bir *güçlü başvuru*, bir nesne ile ilişkili ve geçerli ya da geçersiz olabilir. Çağrı `As()` veya `AsIID()` güçlü bir başvuru almak için yöntemi. Güçlü Başvuru geçerli olduğunda, ilişkili nesne erişebilir. Güçlü Başvuru olduğunda geçersiz (`nullptr`), ilişkili nesne erişilemez.

A `WeakRef` nesne genellikle, varlığı harici bir iş parçacığı ya da uygulama tarafından denetlenen bir nesneyi göstermek için kullanılır. Örneğin, oluşturun bir `WeakRef` nesneden bir dosya nesnesine bir başvuru. Dosya açıkken, güçlü başvuru geçerli değil. Ancak, dosya kapalıysa, güçlü başvuru geçersiz hale gelir.

Davranış değişikliği olduğunu unutmayın [olarak](#as), [Asııd](#asiid) ve [CopyTo](#copyto) Windows 10 SDK'sı yöntemleri. Daha önce bu yöntemlerin herhangi biriyle çağrıldıktan sonra iade edilemedi `WeakRef` için `nullptr` güçlü bir başvuru başarıyla, aşağıdaki kodda gösterildiği gibi edinilen olmadığını belirlemek için:

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)
{
    wprintf(L"Couldn’t get strong ref!");
}
```

Yukarıdaki kod, Windows 10 SDK'sı kullanırken çalışmaz (veya üzeri). Bunun yerine, için geçirilen işaretçiyi denetleyin `nullptr`.

```cpp
if (strongRef == nullptr)
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

`WeakRef`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="tilde-weakref"></a>WeakRef:: ~ WeakRef yok Edicisi

Geçerli örneğinin başlatmasını geri alır `WeakRef` sınıfı.

```cpp
~WeakRef();
```

## <a name="as"></a>WeakRef::As yöntemi

Belirtilen ayarlar `ComPtr` belirtilen arabirim temsil etmek için işaretçi parametresi.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* ptr
);

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr
);
```

### <a name="parameters"></a>Parametreler

*U*<br/>
Bir arabirim kimliği.

*ptr*<br/>
Bu işlem tamamlandığında, parametre temsil eden bir nesne *U*.

### <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT, işlem başarısız oldu, ve *ptr* ayarlanır `nullptr`.

- Geçerli bu işlem başarılı olursa S_OK `WeakRef` nesne zaten yayımlandı. Parametre *ptr* ayarlanır `nullptr`.

- Geçerli bu işlem başarılı olursa S_OK `WeakRef` nesne parametresinden türetilmemiş *U*. Parametre *ptr* ayarlanır `nullptr`.

### <a name="remarks"></a>Açıklamalar

Bir hata varsa yayıldığını parametresi *U* olduğu `IWeakReference`, veya türünden türetilmediğinden `IInspectable`.

İlk şablon kodunuzda kullanması gereken biçimidir. İkinci şablonu olduğu gibi C++ dil özellikleri destekleyen bir iç, Yardımcısı özelleştirmesi [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü yazın.

Windows 10 SDK'SINDAN başlayarak, bu yöntem ayarlı değil `WeakRef` için örnek `nullptr` zayıf başvuru elde edilemedi, bu nedenle, kaçının denetler ve hata denetimi kod `WeakRef` için `nullptr`. Bunun yerine, kontrol *ptr* için `nullptr`.

## <a name="asiid"></a>Weakref::asııd yöntemi

Belirtilen ayarlar `ComPtr` belirtilen arabirim kimliği. temsil etmek için işaretçi parametresi

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
Bir arabirim kimliği.

*ptr*<br/>
Bu işlem tamamlandığında, parametre temsil eden bir nesne *riid*.

### <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT, işlem başarısız oldu, ve *ptr* ayarlanır `nullptr`.

- Geçerli bu işlem başarılı olursa S_OK `WeakRef` nesne zaten yayımlandı. Parametre *ptr* ayarlanır `nullptr`.

- Geçerli bu işlem başarılı olursa S_OK `WeakRef` nesne parametresinden türetilmemiş *riid*. Parametre *ptr* ayarlanır `nullptr`. (Daha fazla bilgi için açıklamalara bakın.)

### <a name="remarks"></a>Açıklamalar

Bir hata varsa yayıldığını parametresi *riid* türünden türetilmediğinden `IInspectable`. Bu hata, dönüş değeri yerine geçer.

İlk şablon kodunuzda kullanması gereken biçimidir. (Burada gösterilen olmasa üst bilgi dosyasında bildirilen) ikinci gibi C++ dil özellikleri destekleyen bir iç, Yardımcısı özelleştirmesi şablonudur [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü yazın.

Windows 10 SDK'SINDAN başlayarak, bu yöntem ayarlı değil `WeakRef` için örnek `nullptr` zayıf başvuru elde edilemedi, bu nedenle, kaçının denetler ve hata denetimi kod `WeakRef` için `nullptr`. Bunun yerine, kontrol *ptr* için `nullptr`.

## <a name="copyto"></a>WeakRef::CopyTo yöntemi

Bir işaretçi bir arabirim için kullanılabiliyorsa, belirtilen bir işaretçi değişkenine atar.

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>Parametreler

*U*<br/>
İşaretçi bir `IInspectable` arabirimi. Bir hata varsa yayıldığını *U* türünden türetilmediğinden `IInspectable`.

*riid*<br/>
Bir arabirim kimliği. Bir hata varsa yayıldığını *riid* türünden türetilmediğinden `IWeakReference`.

*ptr*<br/>
Karakteriyle dolaylı bir işaretçiye `IInspectable` veya `IWeakReference`.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. Daha fazla bilgi için **açıklamalar**.

### <a name="remarks"></a>Açıklamalar

S_OK dönüş değeri, bu işlem başarılı oldu, ancak güçlü bir başvuru zayıf başvuru çözümlendiği olup olmadığını göstermez anlamına gelir. S_OK döndürülürse, bu parametrenin test *p* güçlü bir başvuru; diğer bir deyişle, parametre *p* değerine eşit değildir `nullptr`.

Windows 10 SDK'SINDAN başlayarak, bu yöntem ayarlı değil `WeakRef` için örnek `nullptr` zayıf başvuru elde edilemedi, bu nedenle, kaçının denetleyen kod denetlenirken hata oluştu `WeakRef` için `nullptr`. Bunun yerine, kontrol *ptr* için `nullptr`.

## <a name="operator-ampersand-operator"></a>WeakRef::operator&amp; işleci

Döndürür bir `ComPtrRef` geçerli temsil eden nesne `WeakRef` nesne.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>Dönüş Değeri

A `ComPtrRef` geçerli temsil eden nesne `WeakRef` nesne.

### <a name="remarks"></a>Açıklamalar

Kodunuzda kullanılmak üzere tasarlanmamıştır iç Yardımcısı operatörün budur.

## <a name="weakref"></a>WeakRef::WeakRef Oluşturucusu

Yeni bir örneğini başlatır `WeakRef` sınıfı.

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Bir işaretçi, başvuru veya rvalue başvurusunu geçerli başlatır, varolan bir nesneye `WeakRef` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu boş bir başlatır `WeakRef` nesne. İkinci oluşturucu başlatan bir `WeakRef` işaretçisi nesneden `IWeakReference` arabirimi. Üçüncü Oluşturucu başlatan bir `WeakRef` başvuru nesneden bir `ComPtr<IWeakReference>` nesne. Dördüncü ve beşinci oluşturucular başlatan bir `WeakRef` başka bir nesne `WeakRef` nesne.
