---
title: WeakReference Sınıfı
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::Resolve
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
- implements/Microsoft::WRL::Details::WeakReference::~WeakReference
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
helpviewer_keywords:
- Microsoft::WRL::Details::WeakReference class
- Microsoft::WRL::Details::WeakReference::DecrementStrongReference method
- Microsoft::WRL::Details::WeakReference::IncrementStrongReference method
- Microsoft::WRL::Details::WeakReference::Resolve method
- Microsoft::WRL::Details::WeakReference::SetUnknown method
- Microsoft::WRL::Details::WeakReference::~WeakReference, destructor
- Microsoft::WRL::Details::WeakReference::WeakReference, constructor
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
ms.openlocfilehash: a80c0ec14da2a955a95ac84dd3975212ef20ae04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374213"
---
# <a name="weakreference-class"></a>WeakReference Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
class WeakReference;
```

## <a name="remarks"></a>Açıklamalar

Windows Runtime veya klasik COM ile kullanılabilecek zayıf bir *başvuruyu* temsil eder. Zayıf bir başvuru, erişilebilir veya erişilemeyen bir nesneyi temsil eder.

Bir `WeakReference` nesne, bir nesneye işaretçi olan güçlü bir *başvuru*ve `Resolve()` yöntem tarafından dağıtılan güçlü başvurunun kopya sayısı olan güçlü bir *başvuru sayısı*tutar. Güçlü başvuru sayısı sıfır olmasa da, güçlü başvuru geçerlidir ve nesneye erişilebilir. Güçlü başvuru sayısı sıfır olduğunda, güçlü başvuru geçersiz olur ve nesneye erişilemez.

Nesne `WeakReference` genellikle, varlığı dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil etmek için kullanılır. Örneğin, bir `WeakReference` dosya nesnesine bir başvuru bir nesne oluşturmak. Dosya açıkken, güçlü başvuru geçerlidir. Ancak dosya kapatılırsa, güçlü başvuru geçersiz olur.

Yöntemler `WeakReference` iş parçacığı güvenlidir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                  | Açıklama
----------------------------------------------------- | ---------------------------------------------------------------------------
[ZayıfReferans::WeakReference](#weakreference)        | `WeakReference` sınıfının yeni bir örneğini başlatır.
[Zayıf Referans::~WeakReference](#tilde-weakreference) | `WeakReference` Sınıfın geçerli örneğini deinitialize eder (yok eder).

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                                 | Açıklama
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[WeakReference::DecrementStrongReference](#decrementstrongreference) | Geçerli `WeakReference` nesnenin güçlü başvuru sayısını eriter.
[WeakReference::ArtışStrongReference](#incrementstrongreference) | Geçerli `WeakReference` nesnenin güçlü başvuru sayısını daartışlar.
[ZayıfReferans::Çözümle](#resolve)                                   | Güçlü başvuru sayısı sıfır değilse, belirtilen işaretçiyi geçerli güçlü başvuru değerine ayarlar.
[ZayıfReferans::SetUnknown](#setunknown)                             | Geçerli `WeakReference` nesnenin güçlü başvurularını belirtilen arabirim işaretçisine ayarlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WeakReference`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="weakreferenceweakreference"></a><a name="tilde-weakreference"></a>Zayıf Referans::~WeakReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Sınıfın geçerli örneğini `WeakReference` deinitialize eder.

## <a name="weakreferencedecrementstrongreference"></a><a name="decrementstrongreference"></a>WeakReference::DecrementStrongReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>Açıklamalar

Geçerli `WeakReference` nesnenin güçlü başvuru sayısını eriter.

Güçlü başvuru sayısı sıfır olduğunda, güçlü başvuru `nullptr`.

### <a name="return-value"></a>Dönüş Değeri

Verilen güçlü başvuru sayısı.

## <a name="weakreferenceincrementstrongreference"></a><a name="incrementstrongreference"></a>WeakReference::ArtışStrongReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>Dönüş Değeri

Artan güçlü başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Geçerli `WeakReference` nesnenin güçlü başvuru sayısını daartışlar.

## <a name="weakreferenceresolve"></a><a name="resolve"></a>ZayıfReferans::Çözümle

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arayüz kimliği.

*ppvNesne*<br/>
Bu işlem tamamlandığında, güçlü başvuru sayısı sıfır değilse geçerli güçlü başvurunun bir kopyası.

### <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı ve güçlü başvuru sayısı sıfır ise S_OK. *ppvObject* parametresi `nullptr`.

- Bu işlem başarılı ve güçlü başvuru sayısı sıfır değilse S_OK. *ppvObject* parametresi güçlü başvuru olarak ayarlanır.

- Aksi takdirde, bu işlemin başarısız olmasının nedenini gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Güçlü başvuru sayısı sıfır değilse, belirtilen işaretçiyi geçerli güçlü başvuru değerine ayarlar.

## <a name="weakreferencesetunknown"></a><a name="setunknown"></a>ZayıfReferans::SetUnknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>Parametreler

*Unk*<br/>
Bir nesnenin `IUnknown` arabirimine işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli `WeakReference` nesnenin güçlü başvurularını belirtilen arabirim işaretçisine ayarlar.

## <a name="weakreferenceweakreference"></a><a name="weakreference"></a>ZayıfReferans::WeakReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
WeakReference();
```

### <a name="remarks"></a>Açıklamalar

`WeakReference` sınıfının yeni bir örneğini başlatır.

Nesne için güçlü `WeakReference` başvuru işaretçisi baş harfe `nullptr`ve güçlü başvuru sayısı 1'e başolarak başolarak verilir.
