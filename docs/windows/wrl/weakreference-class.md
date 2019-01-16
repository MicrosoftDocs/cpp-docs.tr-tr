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
ms.openlocfilehash: a3372a176a158dd9c89eb888c8deb0244eef9a84
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335202"
---
# <a name="weakreference-class"></a>WeakReference Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class WeakReference;
```

## <a name="remarks"></a>Açıklamalar

Temsil eden bir *zayıf başvuru* kullanılabilen Windows çalışma zamanı veya klasik COM ile Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.

A `WeakReference` nesne tutar bir *güçlü başvuru*, bir nesneye bir işaretçi olduğu ve bir *güçlü başvuru sayısı*, kopya tarafından dağıtılan güçlü başvuru sayısını olduğu `Resolve()` yöntemi. Güçlü Başvuru sayısı sıfır dışında olsa da, güçlü başvuru geçerli olduğundan ve erişilebilir bir nesnedir. Güçlü Başvuru sayısı sıfır olduğunda, güçlü başvuru geçersiz ve nesne erişilemez.

A `WeakReference` nesne genellikle, varlığı harici bir iş parçacığı ya da uygulama tarafından denetlenen bir nesneyi göstermek için kullanılır. Örneğin, oluşturun bir `WeakReference` nesneden bir dosya nesnesine bir başvuru. Dosya açıkken, güçlü başvuru geçerli değil. Ancak, dosya kapalıysa, güçlü başvuru geçersiz hale gelir.

`WeakReference` Yöntemlerdir iş parçacığı açısından güvenlidir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                  | Açıklama
----------------------------------------------------- | ---------------------------------------------------------------------------
[WeakReference::WeakReference](#weakreference)        | Yeni bir örneğini başlatır `WeakReference` sınıfı.
[WeakReference:: ~ WeakReference](#tilde-weakreference) | Başlatılmasını geri alır (yok eder), geçerli örneğini `WeakReference` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                                 | Açıklama
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[WeakReference::DecrementStrongReference](#decrementstrongreference) | Güçlü Başvuru geçerli sayısını azaltır `WeakReference` nesne.
[Weakreference::ıncrementstrongreference](#incrementstrongreference) | Geçerli güçlü başvuru sayısını artırır `WeakReference` nesne.
[WeakReference::Resolve](#resolve)                                   | Güçlü Başvuru sayısı sıfır değilse belirtilen işaretçi geçerli güçlü başvuru değerine ayarlar.
[WeakReference::SetUnknown](#setunknown)                             | Güçlü Başvuru geçerli ayarlar `WeakReference` belirtilen arabirim işaretçisini için nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WeakReference`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="tilde-weakreference"></a>WeakReference:: ~ WeakReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Geçerli örneğinin başlatmasını geri alır `WeakReference` sınıfı.

## <a name="decrementstrongreference"></a>WeakReference::DecrementStrongReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>Açıklamalar

Güçlü Başvuru geçerli sayısını azaltır `WeakReference` nesne.

Güçlü Başvuru sayısı sıfır olduğunda, güçlü başvuru kümesine `nullptr`.

### <a name="return-value"></a>Dönüş Değeri

İndirildiği güçlü başvuru sayısı.

## <a name="incrementstrongreference"></a>Weakreference::ıncrementstrongreference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>Dönüş Değeri

Artan güçlü başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Geçerli güçlü başvuru sayısını artırır `WeakReference` nesne.

## <a name="resolve"></a>WeakReference::Resolve

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
Bir arabirim kimliği.

*ppvObject*<br/>
Bu işlem tamamlandığında bir kopyasını güçlü başvuru sayısı sıfır değilse geçerli güçlü başvuru.

### <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır olan. *PpvObject* parametrenin ayarlanmış `nullptr`.

- Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır. *PpvObject* parametre güçlü başvuru.

- Aksi takdirde, nedenini belirten bir HRESULT, bu işlem başarısız oldu.

### <a name="remarks"></a>Açıklamalar

Güçlü Başvuru sayısı sıfır değilse belirtilen işaretçi geçerli güçlü başvuru değerine ayarlar.

## <a name="setunknown"></a>WeakReference::SetUnknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>Parametreler

*UNK*<br/>
Bir işaretçi `IUnknown` bir nesnenin arabirimi.

### <a name="remarks"></a>Açıklamalar

Güçlü Başvuru geçerli ayarlar `WeakReference` belirtilen arabirim işaretçisini için nesne.

## <a name="weakreference"></a>WeakReference::WeakReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
WeakReference();
```

### <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır `WeakReference` sınıfı.

Güçlü başvuru işaretçisi `WeakReference` nesne için başlatılan `nullptr`, ve güçlü başvuru sayısı 1 olarak başlatılır.
