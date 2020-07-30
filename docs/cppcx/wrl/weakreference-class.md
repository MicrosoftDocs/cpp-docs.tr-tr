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
ms.openlocfilehash: 9a367a61a029abe1be599b1e262e279402149ccd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220463"
---
# <a name="weakreference-class"></a>WeakReference Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
class WeakReference;
```

## <a name="remarks"></a>Açıklamalar

Windows Çalışma Zamanı veya klasik COM ile kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.

Bir `WeakReference` nesnesi, bir nesnesi işaretçisi olan *güçlü*bir başvuru ve yöntemi tarafından dağıtılan güçlü başvurunun kopya sayısı olan güçlü bir *başvuru sayısı*tutar `Resolve()` . Güçlü başvuru sayısı sıfır dışında olduğunda, güçlü başvuru geçerlidir ve nesneye erişilebilir. Tanımlayıcı başvuru sayısı sıfır olduğunda, güçlü başvuru geçersizdir ve nesneye erişilemez.

Bir `WeakReference` nesne, genellikle varlığı bir dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil etmek için kullanılır. Örneğin, bir `WeakReference` dosya nesnesine başvurudan bir nesne oluşturun. Dosya açıkken, güçlü başvuru geçerli olur. Ancak dosya kapalıysa, güçlü başvuru geçersiz hale gelir.

`WeakReference`Yöntemler iş parçacığı güvenlidir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                  | Açıklama
----------------------------------------------------- | ---------------------------------------------------------------------------
[WeakReference:: WeakReference](#weakreference)        | `WeakReference` sınıfının yeni bir örneğini başlatır.
[WeakReference:: ~ WeakReference](#tilde-weakreference) | Sınıfın geçerli örneğini kaldırır (yok eder) `WeakReference` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                                 | Açıklama
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[WeakReference::D ecrementStrongReference](#decrementstrongreference) | Geçerli nesnenin tanımlayıcı başvuru sayısını azaltır `WeakReference` .
[WeakReference:: IncrementStrongReference](#incrementstrongreference) | Geçerli nesnenin tanımlayıcı başvuru sayısını artırır `WeakReference` .
[WeakReference:: Resolve](#resolve)                                   | Güçlü başvuru sayısı sıfır değilse, belirtilen işaretçiyi geçerli tanımlayıcı başvuru değerine ayarlar.
[WeakReference:: SetUnknown](#setunknown)                             | Geçerli nesnenin güçlü başvurusunu `WeakReference` belirtilen arabirim işaretçisine ayarlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WeakReference`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="weakreferenceweakreference"></a><a name="tilde-weakreference"></a>WeakReference:: ~ WeakReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Sınıfın geçerli örneğini kaldırır `WeakReference` .

## <a name="weakreferencedecrementstrongreference"></a><a name="decrementstrongreference"></a>WeakReference::D ecrementStrongReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesnenin tanımlayıcı başvuru sayısını azaltır `WeakReference` .

Güçlü başvuru sayısı sıfır olduğunda, güçlü başvuru olarak ayarlanır **`nullptr`** .

### <a name="return-value"></a>Dönüş Değeri

Azaltma güçlü başvuru sayısı.

## <a name="weakreferenceincrementstrongreference"></a><a name="incrementstrongreference"></a>WeakReference:: IncrementStrongReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>Dönüş Değeri

Artan tanımlayıcı başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Geçerli nesnenin tanımlayıcı başvuru sayısını artırır `WeakReference` .

## <a name="weakreferenceresolve"></a><a name="resolve"></a>WeakReference:: Resolve

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*ppvObject*<br/>
Bu işlem tamamlandığında, güçlü başvuru sayısı sıfır değilse, geçerli güçlü başvurunun bir kopyası.

### <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı olursa ve tanımlayıcı başvuru sayısı sıfırsa S_OK. *PpvObject* parametresi olarak ayarlanır **`nullptr`** .

- Bu işlem başarılı olursa ve tanımlayıcı başvuru sayısı sıfır değilse S_OK. *PpvObject* parametresi, güçlü başvuru olarak ayarlanır.

- Aksi takdirde, bu işlemin başarısız olma nedenini gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Güçlü başvuru sayısı sıfır değilse, belirtilen işaretçiyi geçerli tanımlayıcı başvuru değerine ayarlar.

## <a name="weakreferencesetunknown"></a><a name="setunknown"></a>WeakReference:: SetUnknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>Parametreler

*unk*<br/>
Bir nesnenin arabirimine yönelik bir işaretçi `IUnknown` .

### <a name="remarks"></a>Açıklamalar

Geçerli nesnenin güçlü başvurusunu `WeakReference` belirtilen arabirim işaretçisine ayarlar.

## <a name="weakreferenceweakreference"></a><a name="weakreference"></a>WeakReference:: WeakReference

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
WeakReference();
```

### <a name="remarks"></a>Açıklamalar

`WeakReference` sınıfının yeni bir örneğini başlatır.

Nesnesi için güçlü başvuru işaretçisi `WeakReference` olarak başlatılır **`nullptr`** ve tanımlayıcı başvuru sayısı 1 olarak başlatılır.
