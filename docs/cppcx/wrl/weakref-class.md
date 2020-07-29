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
ms.openlocfilehash: 715a823784aaa75f9abe349ef0a7ddc9e5d607d1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218357"
---
# <a name="weakref-class"></a>WeakRef Sınıfı

Klasik COM değil yalnızca Windows Çalışma Zamanı tarafından kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::WeakRef Oluşturucusu](#weakref)|`WeakRef` sınıfının yeni bir örneğini başlatır.|
|[WeakRef::~WeakRef Yıkıcısı](#tilde-weakref)|Sınıfın geçerli örneğini kaldırır `WeakRef` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::As Metodu](#as)|Belirtilen bir `ComPtr` arabirimi göstermek için belirtilen işaretçi parametresini ayarlar.|
|[WeakRef::AsIID Metodu](#asiid)|Belirtilen `ComPtr` ARABIRIM kimliğini temsil etmek için belirtilen işaretçi parametresini ayarlar.|
|[WeakRef::CopyTo Metodu](#copyto)|Varsa, belirtilen işaretçi değişkenine bir arabirime bir işaretçi atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::operator& İşleci](#operator-ampersand-operator)|`ComPtrRef`Geçerli nesneyi temsil eden bir nesne döndürür `WeakRef` .|

## <a name="remarks"></a>Açıklamalar

`WeakRef`Nesnesi, bir nesneyle ilişkili olan *güçlü bir başvuruyu*tutar ve geçerli veya geçersiz olabilir. `As()` `AsIID()` Güçlü bir başvuru almak için veya metodunu çağırın. Güçlü başvuru geçerliyse, ilişkili nesneye erişebilir. Güçlü başvuru geçersiz olduğunda ( **`nullptr`** ), ilişkili nesne erişilemez olur.

Bir `WeakRef` nesne, genellikle varlığı bir dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil etmek için kullanılır. Örneğin, bir `WeakRef` dosya nesnesine başvurudan bir nesne oluşturun. Dosya açıkken, güçlü başvuru geçerli olur. Ancak dosya kapalıysa, güçlü başvuru geçersiz hale gelir.

Windows 10 SDK 'daki [as](#as), [AsIID](#asiid) ve [CopyTo](#copyto) yöntemlerinde bir davranış değişikliği olduğunu unutmayın. Daha önce, bu yöntemlerden herhangi birini çağırdıktan sonra, `WeakRef` **`nullptr`** aşağıdaki kodda olduğu gibi, güçlü bir başvurunun başarıyla alınıp alınmadığını öğrenmek için ' a bakabilirsiniz:

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

Yukarıdaki kod, Windows 10 SDK (veya üzeri) kullanılırken çalışmaz. Bunun yerine, için geçirilen işaretçiyi kontrol edin **`nullptr`** .

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

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="weakrefweakref-destructor"></a><a name="tilde-weakref"></a>WeakRef:: ~ WeakRef yıkıcısı

Sınıfın geçerli örneğini kaldırır `WeakRef` .

```cpp
~WeakRef();
```

## <a name="weakrefas-method"></a><a name="as"></a>WeakRef:: as yöntemi

Belirtilen bir `ComPtr` arabirimi göstermek için belirtilen işaretçi parametresini ayarlar.

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
Arabirim KIMLIĞI.

*ptr*<br/>
Bu işlem tamamlandığında, *U*parametresini temsil eden bir nesne.

### <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı olursa S_OK; Aksi takdirde, işlemin başarısız olmasının nedenini belirten bir HRESULT ve *PTR* olarak ayarlanır **`nullptr`** .

- Bu işlem başarılı olursa, ancak geçerli `WeakRef` nesne zaten yayınlanmışsa S_OK. *PTR* parametresi olarak ayarlanır **`nullptr`** .

- Bu işlem başarılı olursa, ancak geçerli `WeakRef` nesne *U*parametresinden türetilmediği için S_OK. *PTR* parametresi olarak ayarlanır **`nullptr`** .

### <a name="remarks"></a>Açıklamalar

*U* parametresi ise veya türetilmediği takdirde bir hata yayınlanır `IWeakReference` `IInspectable` .

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon, [Otomatik](../../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğü gibi C++ dil özelliklerini destekleyen bir iç, yardımcı özelleşmedir.

Windows 10 SDK ' dan itibaren, bu yöntem, `WeakRef` zayıf başvuru alınamadığından örneği olarak ayarlamaz **`nullptr`** , bu nedenle için öğesini denetleyen hata denetimi kodunu kullanmaktan kaçının `WeakRef` **`nullptr`** . Bunun yerine, için *PTR* 'yi denetleyin **`nullptr`** .

## <a name="weakrefasiid-method"></a><a name="asiid"></a>WeakRef:: AsIID yöntemi

Belirtilen `ComPtr` ARABIRIM kimliğini temsil etmek için belirtilen işaretçi parametresini ayarlar.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*ptr*<br/>
Bu işlem tamamlandığında, parametre *riıd*temsil eden bir nesne.

### <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı olursa S_OK; Aksi takdirde, işlemin başarısız olmasının nedenini belirten bir HRESULT ve *PTR* olarak ayarlanır **`nullptr`** .

- Bu işlem başarılı olursa, ancak geçerli `WeakRef` nesne zaten yayınlanmışsa S_OK. *PTR* parametresi olarak ayarlanır **`nullptr`** .

- Bu işlem başarılı olursa, ancak geçerli `WeakRef` nesne *riıd*parametresinden türetilmediği için S_OK. *PTR* parametresi olarak ayarlanır **`nullptr`** . (Daha fazla bilgi için bkz. açıklamalar.)

### <a name="remarks"></a>Açıklamalar

*Riıd* parametresi öğesinden türetilmediği takdirde bir hata yayınlanır `IInspectable` . Bu hata, dönüş değerinin yerini almıştır.

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon (burada gösterilmez, ancak başlık dosyasında belirtilir), [Otomatik](../../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğü gibi C++ dil özelliklerini destekleyen bir iç, yardımcı özelleşmedir.

Windows 10 SDK ' dan itibaren, bu yöntem, `WeakRef` zayıf başvuru alınamadığından örneği olarak ayarlamaz **`nullptr`** , bu nedenle için öğesini denetleyen hata denetimi kodunu kullanmaktan kaçının `WeakRef` **`nullptr`** . Bunun yerine, için *PTR* 'yi denetleyin **`nullptr`** .

## <a name="weakrefcopyto-method"></a><a name="copyto"></a>WeakRef:: CopyTo yöntemi

Varsa, belirtilen işaretçi değişkenine bir arabirime bir işaretçi atar.

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
Bir `IInspectable` arabirim işaretçisi. *U* öğesinden türetilmediği takdirde bir hata yayınlanır `IInspectable` .

*riıd*<br/>
Arabirim KIMLIĞI. *Riıd* öğesinden türetilmediği takdirde bir hata yayınlanır `IWeakReference` .

*ptr*<br/>
Ya da için, dolaylı olarak dolaylı bir işaretçi `IInspectable` `IWeakReference` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. Daha fazla bilgi için bkz. **açıklamalar**.

### <a name="remarks"></a>Açıklamalar

S_OK dönüş değeri, bu işlemin başarılı olduğu, ancak zayıf başvurunun güçlü bir başvuruya çözümlenip çözümlenmediğini belirtmediği anlamına gelir. S_OK döndürülürse, *p* parametresinin bir güçlü başvuru olduğunu test edin; diğer bir deyişle, *p* parametresi değerine eşit değildir **`nullptr`** .

Windows 10 SDK ' dan itibaren, bu yöntem, `WeakRef` zayıf başvuru alınamadığından örneği olarak ayarlamaz **`nullptr`** , bu nedenle, için öğesini denetleyen hata denetim kodunu kullanmaktan kaçının `WeakRef` **`nullptr`** . Bunun yerine, için *PTR* 'yi denetleyin **`nullptr`** .

## <a name="weakrefoperatoramp-operator"></a><a name="operator-ampersand-operator"></a>WeakRef:: operator &amp; işleci

`ComPtrRef`Geçerli nesneyi temsil eden bir nesne döndürür `WeakRef` .

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>Dönüş Değeri

`ComPtrRef`Geçerli nesneyi temsil eden nesne `WeakRef` .

### <a name="remarks"></a>Açıklamalar

Bu, kodunuzda kullanılması amaçlanan bir iç yardımcı işleçtir.

## <a name="weakrefweakref-constructor"></a><a name="weakref"></a>WeakRef:: WeakRef Oluşturucusu

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

*ptr*<br/>
Geçerli nesneyi Başlatan mevcut nesnesine bir işaretçi, başvuru veya rvalue başvurusu `WeakRef` .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu boş bir nesne başlatır `WeakRef` . İkinci Oluşturucu, bir `WeakRef` nesneyi bir işaretçiden `IWeakReference` arabirime başlatır. Üçüncü Oluşturucu bir nesne başvurusundan bir nesnesi başlatır `WeakRef` `ComPtr<IWeakReference>` . Dördüncü ve beşinci oluşturucular, bir `WeakRef` nesneyi başka bir `WeakRef` nesneden başlatır.
