---
title: ComPtr Sınıfı
ms.date: 07/26/2019
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
- client/Microsoft::WRL::ComPtr::As
- client/Microsoft::WRL::ComPtr::AsIID
- client/Microsoft::WRL::ComPtr::AsWeak
- client/Microsoft::WRL::ComPtr::Attach
- client/Microsoft::WRL::ComPtr::ComPtr
- client/Microsoft::WRL::ComPtr::CopyTo
- client/Microsoft::WRL::ComPtr::Detach
- client/Microsoft::WRL::ComPtr::Get
- client/Microsoft::WRL::ComPtr::GetAddressOf
- client/Microsoft::WRL::ComPtr::InternalAddRef
- client/Microsoft::WRL::ComPtr::InternalRelease
- client/Microsoft::WRL::ComPtr::operator&
- client/Microsoft::WRL::ComPtr::operator->
- client/Microsoft::WRL::ComPtr::operator=
- client/Microsoft::WRL::ComPtr::operator==
- client/Microsoft::WRL::ComPtr::operator!=
- client/Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType
- client/Microsoft::WRL::ComPtr::ptr_
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
- client/Microsoft::WRL::ComPtr::Reset
- client/Microsoft::WRL::ComPtr::Swap
- client/Microsoft::WRL::ComPtr::~ComPtr
helpviewer_keywords:
- Microsoft::WRL::ComPtr class
- Microsoft::WRL::ComPtr::As method
- Microsoft::WRL::ComPtr::AsIID method
- Microsoft::WRL::ComPtr::AsWeak method
- Microsoft::WRL::ComPtr::Attach method
- Microsoft::WRL::ComPtr::ComPtr, constructor
- Microsoft::WRL::ComPtr::CopyTo method
- Microsoft::WRL::ComPtr::Detach method
- Microsoft::WRL::ComPtr::Get method
- Microsoft::WRL::ComPtr::GetAddressOf method
- Microsoft::WRL::ComPtr::InternalAddRef method
- Microsoft::WRL::ComPtr::InternalRelease method
- Microsoft::WRL::ComPtr::operator& operator
- Microsoft::WRL::ComPtr::operator-> operator
- Microsoft::WRL::ComPtr::operator= operator
- Microsoft::WRL::ComPtr::operator== operator
- Microsoft::WRL::ComPtr::operator!= operator
- Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType operator
- Microsoft::WRL::ComPtr::ptr_ data member
- Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf method
- Microsoft::WRL::ComPtr::Reset method
- Microsoft::WRL::ComPtr::Swap method
- Microsoft::WRL::ComPtr::~ComPtr, destructor
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
ms.openlocfilehash: 1e20a991c8f32027aeea6a17df0534aa6e1c2c43
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418323"
---
# <a name="comptr-class"></a>ComPtr Sınıfı

Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türü oluşturur. `ComPtr`, temel alınan arabirim işaretçisi için otomatik olarak bir başvuru sayısı tutar ve başvuru sayısı sıfıra gittiğinde arabirimi yayınlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`ComPtr` temsil eden arabirim.

*Larınız*<br/>
Geçerli `ComPtr` arkadaş olduğu bir sınıf. (Bu parametreyi kullanan şablon korunur.)

## <a name="remarks"></a>Açıklamalar

`ComPtr<>`, temel alınan arabirim işaretçisini temsil eden bir tür bildirir. Bir değişken bildirmek için `ComPtr<>` kullanın ve ardından bir arabirim üye işlevine erişmek için ok üye erişim işlecini (`->`) kullanın.

Akıllı işaretçiler hakkında daha fazla bilgi için MSDN Kitaplığı 'ndaki [com kodlama uygulamaları](/windows/win32/LearnWin32/com-coding-practices) konusunun "com akıllı işaretçiler" alt bölümüne bakın.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Adı            | Açıklama
--------------- | ---------------------------------------------------------------
`InterfaceType` | *T* şablonu parametresi tarafından belirtilen tür için eş anlamlı.

### <a name="public-constructors"></a>Genel Oluşturucular

Adı                             | Açıklama
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr:: ComPtr](#comptr)        | `ComPtr` sınıfının yeni bir örneğini başlattıktan sonra. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.
[ComPtr:: ~ ComPtr](#tilde-comptr) | Bir `ComPtr`örneğini kaldırır.

### <a name="public-methods"></a>Genel Yöntemler

Adı                                                      | Açıklama
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr:: as](#as)                                         | Belirtilen şablon parametresi tarafından tanımlanan arabirimi temsil eden bir `ComPtr` nesnesi döndürür.
[ComPtr:: AsIID](#asiid)                                   | Belirtilen arabirim KIMLIĞI tarafından tanımlanan arabirimi temsil eden bir `ComPtr` nesnesi döndürür.
[ComPtr:: Aszayıf](#asweak)                                 | Geçerli nesneye zayıf bir başvuru alır.
[ComPtr:: Attach](#attach)                                 | Bu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirir.
[ComPtr:: CopyTo](#copyto)                                 | Bu `ComPtr` ilişkili geçerli veya belirtilen arabirimi belirtilen çıkış işaretçisine kopyalar.
[ComPtr::D etach](#detach)                                 | Bu `ComPtr` gösterdiği arabiriminden ilişkilendirir.
[ComPtr:: Get](#get)                                       | Bu `ComPtr`ilişkili arabirime yönelik bir işaretçi alır.
[ComPtr:: GetAddressOf](#getaddressof)                     | Bu `ComPtr`temsil eden arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.
[ComPtr:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | Bu `ComPtr` ilişkili arabirimi serbest bırakır ve sonra yayınlanan arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.
[ComPtr::Reset](#reset)                                   | İşaretçiyle ilgili tüm başvuruları bu `ComPtr`ilişkili arabirime yayınlar.
[ComPtr:: swap](#swap)                                     | Geçerli `ComPtr` tarafından yönetilen arabirimi belirtilen `ComPtr`tarafından yönetilen arabirimle değiştirir.

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                        | Açıklama
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr:: InternalAddRef](#internaladdref)   | Bu `ComPtr`ilişkili arabirimin başvuru sayısını artırır.
[ComPtr:: InternalRelease](#internalrelease) | Bu `ComPtr`ilişkili arabirim üzerinde bir COM serbest bırakma işlemi gerçekleştirir.

### <a name="public-operators"></a>Genel İşleçler

Adı                                                                                           | Açıklama
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr:: operator &](#operator-ampersand)                                                       | Geçerli `ComPtr`adresini alır.
[ComPtr:: operator->](#operator-arrow)                                                          | Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.
[ComPtr:: operator =](#operator-assign)                                                          | Geçerli `ComPtr`bir değer atar.
[ComPtr:: operator = =](#operator-equality)                                                       | İki `ComPtr` nesnesinin eşit olup olmadığını gösterir.
[ComPtr:: operator! =](#operator-inequality)                                                     | İki `ComPtr` nesnesinin eşit olup olmadığını gösterir.
[ComPtr:: operator Microsoft:: WRL::D euçlar:: BoolType](#operator-microsoft-wrl-details-booltype) | Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini belirtir.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Adı                 | Açıklama
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::p tr_](#ptr) | İle ilişkili arabirime yönelik bir işaretçi içerir ve bu `ComPtr`yönetilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="tilde-comptr"></a>ComPtr:: ~ ComPtr

Bir `ComPtr`örneğini kaldırır.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>ComPtr:: as

Belirtilen şablon parametresi tarafından tanımlanan arabirimi temsil eden bir `ComPtr` nesnesi döndürür.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* p
) const;

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> p
) const;
```

### <a name="parameters"></a>Parametreler

*Larınız*<br/>
*P*parametresine göre temsil edilecek arabirim.

*Lama*<br/>
*U*parametresi tarafından belirtilen arabirimi temsil eden `ComPtr` nesne. *P* parametresi geçerli `ComPtr` nesnesine başvurmamalıdır.

### <a name="remarks"></a>Açıklamalar

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon, [Otomatik](../../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğü gibi dil özelliklerini C++ destekleyen bir iç, yardımcı özelleşmedir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="asiid"></a>ComPtr:: AsIID

Belirtilen arabirim KIMLIĞI tarafından tanımlanan arabirimi temsil eden bir `ComPtr` nesnesi döndürür.

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*Lama*<br/>
Nesnede, KIMLIĞI *riıd*değerine eşit olan bir arabirim varsa, bu, *riıd* parametresi tarafından belirtilen arabirime yönelik, tam olarak dolaylı bir işaretçi olan. Aksi takdirde, `IUnknown`için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="asweak"></a>ComPtr:: Aszayıf

Geçerli nesneye zayıf bir başvuru alır.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>Parametreler

*pWeakRef*<br/>
Bu işlem tamamlandığında, zayıf başvuru nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="attach"></a>ComPtr:: Attach

Bu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirir.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Bir arabirim türü.

## <a name="comptr"></a>ComPtr:: ComPtr

`ComPtr` sınıfının yeni bir örneğini başlattıktan sonra. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.

```cpp
WRL_NOTHROW ComPtr();

WRL_NOTHROW ComPtr(
   decltype(__nullptr)
);

template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);

WRL_NOTHROW ComPtr(
   const ComPtr& other
);

template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);

WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);

template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other, typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);
```

### <a name="parameters"></a>Parametreler

*Larınız*<br/>
*Diğer* parametrenin türü.

*farklı*<br/>
*U*türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan oluşturucudur, bu implictly boş bir nesne oluşturur. İkinci Oluşturucu açık bir şekilde boş bir nesne oluşturan [__nullptr](../../extensions/nullptr-cpp-component-extensions.md)belirtir.

Üçüncü Oluşturucu, bir işaretçi tarafından belirtilen nesneden bir nesne oluşturur. ComPtr artık, işaret edilen belleğe sahiptir ve ona bir başvuru sayısı tutar.

Dördüncü ve beşinci oluşturucular kopya oluşturuculardır. Beşinci Oluşturucu geçerli türe dönüştürülebilir bir nesneyi kopyalar.

Altıncı ve yedinci oluşturucular taşıma oluşturuculardır. Yedinci Oluşturucu geçerli türe dönüştürülebilir bir nesneyi taşımaktır.

## <a name="copyto"></a>ComPtr:: CopyTo

Bu `ComPtr` ilişkili geçerli veya belirtilen arabirimi belirtilen işaretçiye kopyalar.

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>Parametreler

*Larınız*<br/>
Bir tür adı.

*ptr*<br/>
Bu işlem tamamlandığında, istenen arabirime yönelik bir işaretçi.

*riıd*<br/>
Arabirim KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, örtük `QueryInterface` işleminin neden başarısız olduğunu belirten bir HRESULT.

### <a name="remarks"></a>Açıklamalar

İlk işlev, bu `ComPtr`ilişkili arabirime işaretçinin bir kopyasını döndürür. Bu işlev her zaman S_OK döndürür.

İkinci işlev, *riıd* parametresi tarafından belirtilen arabirim için bu `ComPtr` ilişkili arabirimde `QueryInterface` işlem gerçekleştirir.

Üçüncü işlev *U* parametresinin temel arabirimi için bu `ComPtr` ilişkili arabirimde `QueryInterface` işlem gerçekleştirir.

## <a name="detach"></a>ComPtr::D etach

Bu `ComPtr` nesnesini temsil ettiği arabirimden kaldırır.

```cpp
T* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `ComPtr` nesnesi tarafından temsil edilen arabirime yönelik bir işaretçi.

## <a name="get"></a>ComPtr:: Get

Bu `ComPtr`ilişkili arabirime yönelik bir işaretçi alır.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `ComPtr`ilişkili arabirime yönelik işaretçi.

## <a name="getaddressof"></a>ComPtr:: GetAddressOf

Bu `ComPtr`temsil eden arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bir değişkenin adresi.

## <a name="internaladdref"></a>ComPtr:: InternalAddRef

Bu `ComPtr`ilişkili arabirimin başvuru sayısını artırır.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="internalrelease"></a>ComPtr:: InternalRelease

Bu `ComPtr`ilişkili arabirim üzerinde bir COM serbest bırakma işlemi gerçekleştirir.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="operator-ampersand"></a>ComPtr:: operator&amp;

Bu `ComPtr` nesnesiyle ilişkili arabirimi serbest bırakır ve sonra `ComPtr` nesnesinin adresini alır.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtr`zayıf bir başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu yöntemin arabirim işaretçisine bir başvuru yayınlarsa [ComPtr:: GetAddressOf](#getaddressof) öğesinden farklıdır. Arabirim işaretçisinin adresine ihtiyacınız olduğunda, ancak bu arabirimi yayınlamak istemediğinizde `ComPtr::GetAddressOf` kullanın.

## <a name="operator-arrow"></a>ComPtr:: operator-&gt;

Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli şablon türü adı tarafından belirtilen türe yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi, STDMETHOD makrosunu kullanarak oluşan gereksiz yükü kaldırır. Bu işlev, `virtual`yerine `private` `IUnknown` türlerini yapar.

## <a name="operator-assign"></a>ComPtr:: operator =

Geçerli `ComPtr`bir değer atar.

```cpp
WRL_NOTHROW ComPtr& operator=(
   decltype(__nullptr)
);
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ T *other
);
template <typename U>
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr& operator=(
   const ComPtr &other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   const ComPtr<U>& other
);
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr<U>&& other
);
```

### <a name="parameters"></a>Parametreler

*Larınız*<br/>
Bir sınıf.

*farklı*<br/>
Türe veya başka bir `ComPtr`işaretçi, başvuru veya rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtr`bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlecin ilk sürümü geçerli `ComPtr`boş bir değer atar.

İkinci sürümde, atama arabirimi işaretçisi geçerli `ComPtr` arabirim işaretçiyle aynı değilse, ikinci arabirim işaretçisi geçerli `ComPtr`atanır.

Üçüncü sürümde, atama arabirimi işaretçisi geçerli `ComPtr`atanır.

Dördüncü sürümde, atama değerinin arabirim işaretçisi geçerli `ComPtr` arabirim işaretçiyle aynı değilse, ikinci arabirim işaretçisi geçerli `ComPtr`atanır.

Beşinci sürüm bir kopya işleçtir; geçerli `ComPtr``ComPtr` bir başvuru atanır.

Altıncı sürüm, taşıma semantiğini kullanan bir kopya işleçtir; herhangi bir tür statik atama ise ve sonra geçerli `ComPtr`atanırsa bir `ComPtr` rvalue başvurusu.

Yedinci sürüm, taşıma semantiğini kullanan bir kopya işleçtir; *U* türü `ComPtr` için bir rvalue başvurusu statik cast ve geçerli `ComPtr`atanır.

## <a name="operator-equality"></a>ComPtr:: operator = =

İki `ComPtr` nesnesinin eşit olup olmadığını gösterir.

```cpp
bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Parametreler

*a*<br/>
`ComPtr` nesnesine bir başvuru.

*kenarı*<br/>
Başka bir `ComPtr` nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, nesne *b* *nesnesine eşitse* `true` verir; Aksi takdirde, `false`.

İkinci ve üçüncü işleçler, nesne *a* `nullptr`eşitse `true` yield; Aksi takdirde, `false`.

## <a name="operator-inequality"></a>ComPtr:: operator! =

İki `ComPtr` nesnesinin eşit olup olmadığını gösterir.

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Parametreler

*a*<br/>
`ComPtr` nesnesine bir başvuru.

*kenarı*<br/>
Başka bir `ComPtr` nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, *a* nesnesi *b*nesnesine eşit değilse `true` verir; Aksi takdirde, `false`.

İkinci ve üçüncü işleçler `true`, nesne *a* `nullptr`eşit değilse yield; Aksi takdirde, `false`.

## <a name="operator-microsoft-wrl-details-booltype"></a>ComPtr:: operator Microsoft:: WRL::D euçlar:: BoolType

Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini belirtir.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir arabirim bu `ComPtr`ilişkili ise [BoolStruct:: member](boolstruct-structure.md#member) veri üyesinin adresi; Aksi takdirde, `nullptr`.

## <a name="ptr"></a>ComPtr::p tr_

İle ilişkili arabirime yönelik bir işaretçi içerir ve bu `ComPtr`yönetilir.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Açıklamalar

`ptr_`, dahili, korunan bir veri üyesidir.

## <a name="releaseandgetaddressof"></a>ComPtr:: ReleaseAndGetAddressOf

Bu `ComPtr` ilişkili arabirimi serbest bırakır ve sonra yayınlanan arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `ComPtr`[ptr_](#ptr) veri üyesinin adresi.

## <a name="reset"></a>ComPtr:: Reset

İşaretçiyle ilgili tüm başvuruları bu `ComPtr`ilişkili arabirime yayınlar.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Dönüş Değeri

Varsa, yayınlanan başvuruların sayısı.

## <a name="swap"></a>ComPtr:: swap

Geçerli `ComPtr` tarafından yönetilen arabirimi belirtilen `ComPtr`tarafından yönetilen arabirimle değiştirir.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir `ComPtr`.

