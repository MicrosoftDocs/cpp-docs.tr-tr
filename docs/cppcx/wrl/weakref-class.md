---
title: WeakRef Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
ms.openlocfilehash: 681f5a64c3e2902c66facbd4f0ac3a3663a7e79d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374249"
---
# <a name="weakref-class"></a>WeakRef Sınıfı

Klasik COM'u değil, yalnızca Windows Runtime tarafından kullanılabilecek zayıf bir *başvuruyu* temsil eder. Zayıf bir başvuru, erişilebilir veya erişilemeyen bir nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[WeakRef::WeakRef Oluşturucusu](#weakref)|`WeakRef` sınıfının yeni bir örneğini başlatır.|
|[WeakRef::~WeakRef Yıkıcısı](#tilde-weakref)|Sınıfın geçerli örneğini `WeakRef` deinitialize eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[WeakRef::As Metodu](#as)|Belirtilen arabirimi temsil etmek için belirtilen `ComPtr` işaretçi parametresini ayarlar.|
|[WeakRef::AsIID Metodu](#asiid)|Belirtilen arabirim kimliğini temsil etmek için belirtilen `ComPtr` işaretçi parametresini ayarlar.|
|[WeakRef::CopyTo Metodu](#copyto)|Bir arabirime işaretçi atayan, varsa, belirtilen işaretçi değişkenine.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[WeakRef::operator& İşleci](#operator-ampersand-operator)|Geçerli `WeakRef` `ComPtrRef` nesneyi temsil eden bir nesne döndürür.|

## <a name="remarks"></a>Açıklamalar

Bir `WeakRef` nesne, bir nesneyle ilişkili ve geçerli veya geçersiz olabilecek güçlü bir *başvuru*tutar. Güçlü `As()` bir `AsIID()` başvuru elde etmek için veya yöntemi arayın. Güçlü başvuru geçerli olduğunda, ilişkili nesneye erişebilir. Güçlü başvuru geçersiz olduğunda`nullptr`( ), ilişkili nesneye erişilemez.

Nesne `WeakRef` genellikle, varlığı dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil etmek için kullanılır. Örneğin, bir `WeakRef` dosya nesnesine bir başvuru bir nesne oluşturmak. Dosya açıkken, güçlü başvuru geçerlidir. Ancak dosya kapatılırsa, güçlü başvuru geçersiz olur.

Windows 10 SDK'daki [As](#as), [AsIID](#asiid) ve [CopyTo](#copyto) yöntemlerinde bir davranış değişikliği olduğunu unutmayın. Daha önce, bu yöntemlerden herhangi birini `WeakRef` aradıktan sonra, aşağıdaki kodda olduğu gibi güçlü bir başvurunun başarıyla elde edilip edilemediğinizi belirlemek için `nullptr`

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

Yukarıdaki kod, Windows 10 SDK (veya daha sonra) kullanırken çalışmaz. Bunun yerine, '' için `nullptr`geçirilen işaretçiyi denetleyin.

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

**Üstbilgi:** client.h

**Ad alanı:** Microsoft::WRL

## <a name="weakrefweakref-destructor"></a><a name="tilde-weakref"></a>WeakRef::~WeakRef Yıkıcı

Sınıfın geçerli örneğini `WeakRef` deinitialize eder.

```cpp
~WeakRef();
```

## <a name="weakrefas-method"></a><a name="as"></a>WeakRef::Yöntem olarak

Belirtilen arabirimi temsil etmek için belirtilen `ComPtr` işaretçi parametresini ayarlar.

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
Arayüz kimliği.

*Ptr*<br/>
Bu işlem tamamlandığında, *U*parametreyi temsil eden bir nesne.

### <a name="return-value"></a>Dönüş Değeri

- bu işlem başarılı olursa S_OK; aksi takdirde, işlemin başarısız olmasının nedenini gösteren bir HRESULT ve *ptr'* ye `nullptr`ayarlanır.

- Bu işlem başarılı olursa S_OK, `WeakRef` ancak geçerli nesne zaten serbest bırakıldı. Parametre *ptr* ayarlanır `nullptr`.

- bu işlem başarılı olursa S_OK, `WeakRef` ancak geçerli nesne *U*parametresinden türetilmiş değildir. Parametre *ptr* ayarlanır `nullptr`.

### <a name="remarks"></a>Açıklamalar

*U* `IWeakReference`parametresi veya türetilmiş değilse bir hata `IInspectable`yayılır.

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon, [otomatik](../../cpp/auto-cpp.md) tür tümdengelimi anahtar sözcüğü gibi C++ dil özelliklerini destekleyen dahili, yardımcı uzmanlıktır.

Windows 10 SDK'dan başlayarak, bu `WeakRef` yöntem `nullptr` zayıf başvuru nun alınıp alınamadığını belirtmez, bu `WeakRef` nedenle `nullptr`içini denetleyen hata denetimi kodundan kaçınmanız gerekir. Bunun yerine, *ptr* için kontrol edin. `nullptr`

## <a name="weakrefasiid-method"></a><a name="asiid"></a>WeakRef::AsiID Yöntemi

Belirtilen arabirim kimliğini temsil etmek için belirtilen `ComPtr` işaretçi parametresini ayarlar.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arayüz kimliği.

*Ptr*<br/>
Bu işlem tamamlandığında, parametre *riid*temsil eden bir nesne .

### <a name="return-value"></a>Dönüş Değeri

- bu işlem başarılı olursa S_OK; aksi takdirde, işlemin başarısız olmasının nedenini gösteren bir HRESULT ve *ptr'* ye `nullptr`ayarlanır.

- Bu işlem başarılı olursa S_OK, `WeakRef` ancak geçerli nesne zaten serbest bırakıldı. Parametre *ptr* ayarlanır `nullptr`.

- bu işlem başarılı olursa S_OK, `WeakRef` ancak geçerli nesne parametre *riid*türetilmiş değildir. Parametre *ptr* ayarlanır `nullptr`. (Daha fazla bilgi için Bkz. Açıklamalar.)

### <a name="remarks"></a>Açıklamalar

Parametre *riid* türetilmiş değilse bir hata `IInspectable`yayılan . Bu hata, iade değerinin yerini adar.

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon (burada gösterilmez, ancak üstbilgi dosyasında bildirilir) [otomatik](../../cpp/auto-cpp.md) tür tümdengelim anahtar sözcüğü gibi C++ dil özelliklerini destekleyen dahili, yardımcı uzmanlıktır.

Windows 10 SDK'dan başlayarak, bu `WeakRef` yöntem `nullptr` zayıf başvuru nun alınıp alınamadığını belirtmez, bu `WeakRef` nedenle `nullptr`içini denetleyen hata denetimi kodundan kaçınmanız gerekir. Bunun yerine, *ptr* için kontrol edin. `nullptr`

## <a name="weakrefcopyto-method"></a><a name="copyto"></a>WeakRef::CopyTo Yöntemi

Bir arabirime işaretçi atayan, varsa, belirtilen işaretçi değişkenine.

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
Bir `IInspectable` arabirim işaretle. *U* türetilmiş değilse bir hata `IInspectable`yayılır.

*Riid*<br/>
Arayüz kimliği. *Riid* türetilmiş değilse bir hata `IWeakReference`yayılır.

*Ptr*<br/>
Bir iki kat-dolaylı `IInspectable` işaretçi `IWeakReference`veya .

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT. Daha fazla bilgi için **Açıklamalar'a**bakın.

### <a name="remarks"></a>Açıklamalar

S_OK'nin geri dönüş değeri, bu işlemin başarılı olduğu anlamına gelir, ancak zayıf başvurunun güçlü bir başvuruyla çözülüp çözülmediğini göstermez. S_OK döndürülürse, *p* parametresi güçlü bir başvuru olduğunu sınlayın; diğer bir şey, parametre *p'* ye `nullptr`eşit değildir.

Windows 10 SDK'dan başlayarak, bu `WeakRef` yöntem `nullptr` zayıf başvuru nun alınıp alınamadığını belirtmez, bu `WeakRef` `nullptr`nedenle içini denetleyen hata denetimi kodundan kaçınmanız gerekir. Bunun yerine, *ptr* için kontrol edin. `nullptr`

## <a name="weakrefoperatoramp-operator"></a><a name="operator-ampersand-operator"></a>WeakRef::operatör&amp; Operatörü

Geçerli `WeakRef` `ComPtrRef` nesneyi temsil eden bir nesne döndürür.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtrRef` `WeakRef` nesneyi temsil eden bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu, kodunuzda kullanılmaması gereken bir dahili yardımcı işleçtir.

## <a name="weakrefweakref-constructor"></a><a name="weakref"></a>WeakRef::WeakRef Yapıcı

`WeakRef` sınıfının yeni bir örneğini başlatır.

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

*Ptr*<br/>
Geçerli `WeakRef` nesneyi başharfe atan varolan bir nesneye işaretçi, başvuru veya rvalue-başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu boş `WeakRef` bir nesneyi baş harfe doğru laştırır. İkinci oluşturucu bir işaretçiden arabirime bir `WeakRef` nesneyi başharfe `IWeakReference` yönlendirir. Üçüncü oluşturucu bir `WeakRef` nesneyi bir nesneye `ComPtr<IWeakReference>` başvurudan başharfe ait hale getirmek. Dördüncü ve beşinci kurucular başka `WeakRef` `WeakRef` bir nesneden bir nesneyi başharfe alarlar.
