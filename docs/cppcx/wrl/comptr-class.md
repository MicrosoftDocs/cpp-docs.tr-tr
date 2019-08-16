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
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498407"
---
# <a name="comptr-class"></a>ComPtr Sınıfı

Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türü oluşturur. `ComPtr`, temel alınan arabirim işaretçisi için bir başvuru sayısını otomatik olarak tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parametreler

*ŞI*<br/>
`ComPtr` Temsil eden arabirim.

*LARINIZ*<br/>
Geçerli `ComPtr` bir arkadaş olan sınıf. (Bu parametreyi kullanan şablon korunur.)

## <a name="remarks"></a>Açıklamalar

`ComPtr<>`temel alınan arabirim işaretçisini temsil eden bir tür bildirir. Bir `ComPtr<>` değişken bildirmek için kullanın ve ardından bir arabirim üye işlevine erişmek için ok üye`->`erişim işlecini () kullanın.

Akıllı işaretçiler hakkında daha fazla bilgi için MSDN Kitaplığı 'ndaki [com kodlama uygulamaları](/windows/win32/LearnWin32/com-coding-practices) konusunun "com akıllı işaretçiler" alt bölümüne bakın.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad            | Açıklama
--------------- | ---------------------------------------------------------------
`InterfaceType` | *T* şablonu parametresi tarafından belirtilen tür için eş anlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                             | Açıklama
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr:: ComPtr](#comptr)        | `ComPtr` Sınıfının yeni bir örneğini sonlandırır. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.
[ComPtr:: ~ ComPtr](#tilde-comptr) | Bir örneğini `ComPtr`kaldırır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                      | Açıklama
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr:: as](#as)                                         | Belirtilen şablon `ComPtr` parametresi tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.
[ComPtr:: AsIID](#asiid)                                   | Belirtilen arabirim `ComPtr` kimliği tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.
[ComPtr:: Aszayıf](#asweak)                                 | Geçerli nesneye zayıf bir başvuru alır.
[ComPtr:: Attach](#attach)                                 | Bunu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirir.
[ComPtr:: CopyTo](#copyto)                                 | Bu `ComPtr` ile ilişkili geçerli veya belirtilen arabirimi belirtilen çıkış işaretçisine kopyalar.
[ComPtr::D etach](#detach)                                 | Bunu `ComPtr` temsil eden arabirimden kaldırır.
[ComPtr:: Get](#get)                                       | Bu `ComPtr`ile ilişkili arabirime bir işaretçi alır.
[ComPtr:: GetAddressOf](#getaddressof)                     | Bu`ComPtr`tarafından temsil edilen arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.
[ComPtr:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | , Bununla ilişkili `ComPtr` arabirimi yayınlar ve sonra yayınlanan arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.
[ComPtr::Reset](#reset)                                   | İşaretçiyle ilişkili olan arabirime yönelik tüm başvuruları yayınlar `ComPtr`.
[ComPtr:: swap](#swap)                                     | Geçerli `ComPtr` tarafından yönetilen arabirimi, belirtilen `ComPtr`arabirimiyle yönetilen arabirim ile değiştirir.

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                        | Açıklama
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr:: InternalAddRef](#internaladdref)   | Bununla ilişkili `ComPtr`arabirimin başvuru sayısını artırır.
[ComPtr:: InternalRelease](#internalrelease) | Bu `ComPtr`ile ilişkili ARABIRIM üzerinde bir com yayın işlemi gerçekleştirir.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                                                           | Açıklama
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr:: operator &](#operator-ampersand)                                                       | Geçerli `ComPtr`öğesinin adresini alır.
[ComPtr:: operator->](#operator-arrow)                                                          | Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.
[ComPtr:: operator =](#operator-assign)                                                          | Geçerli `ComPtr`bir değer atar.
[ComPtr:: operator = =](#operator-equality)                                                       | İki `ComPtr` nesnenin eşit olup olmadığını gösterir.
[ComPtr:: operator! =](#operator-inequality)                                                     | İki `ComPtr` nesnenin eşit olup olmadığını gösterir.
[ComPtr:: operator Microsoft:: WRL::D euçlar:: BoolType](#operator-microsoft-wrl-details-booltype) | Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini belirtir.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                 | Açıklama
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::p tr_](#ptr) | İle ilişkili arabirime yönelik bir işaretçi içerir ve bu `ComPtr`ile yönetilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Uzayına** Microsoft:: WRL

## <a name="tilde-comptr"></a>ComPtr:: ~ ComPtr

Bir örneğini `ComPtr`kaldırır.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>ComPtr:: as

Belirtilen şablon `ComPtr` parametresi tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.

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

*LARINIZ*<br/>
*P*parametresine göre temsil edilecek arabirim.

*p*<br/>
*U parametresi*tarafından belirtilen arabirimi temsil eden `ComPtr` nesne. *P* parametresi geçerli `ComPtr` nesneye başvurmamalıdır.

### <a name="remarks"></a>Açıklamalar

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon, [Otomatik](../../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğü gibi dil özelliklerini C++ destekleyen bir iç, yardımcı özelleşmedir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="asiid"></a>ComPtr:: AsIID

Belirtilen arabirim `ComPtr` kimliği tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*p*<br/>
Nesnede, KIMLIĞI *riıd*değerine eşit olan bir arabirim varsa, bu, *riıd* parametresi tarafından belirtilen arabirime yönelik, tam olarak dolaylı bir işaretçi olan. Aksi takdirde, için `IUnknown`bir işaretçisi.

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

Bunu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirir.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Bir arabirim türü.

## <a name="comptr"></a>ComPtr:: ComPtr

`ComPtr` Sınıfının yeni bir örneğini sonlandırır. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.

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

*LARINIZ*<br/>
*Diğer* parametrenin türü.

*farklı*<br/>
*U*türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan oluşturucudur, bu implictly boş bir nesne oluşturur. İkinci Oluşturucu, açık bir şekilde boş bir nesne oluşturan [__nullptr](../../extensions/nullptr-cpp-component-extensions.md)belirtir.

Üçüncü Oluşturucu, bir işaretçi tarafından belirtilen nesneden bir nesne oluşturur. ComPtr artık, işaret edilen belleğe sahiptir ve ona bir başvuru sayısı tutar.

Dördüncü ve beşinci oluşturucular kopya oluşturuculardır. Beşinci Oluşturucu geçerli türe dönüştürülebilir bir nesneyi kopyalar.

Altıncı ve yedinci oluşturucular taşıma oluşturuculardır. Yedinci Oluşturucu geçerli türe dönüştürülebilir bir nesneyi taşımaktır.

## <a name="copyto"></a>ComPtr:: CopyTo

Bu `ComPtr` ile ilişkili geçerli veya belirtilen arabirimi belirtilen işaretçiye kopyalar.

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

*LARINIZ*<br/>
Bir tür adı.

*ptr*<br/>
Bu işlem tamamlandığında, istenen arabirime yönelik bir işaretçi.

*riıd*<br/>
Arabirim KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, örtük `QueryInterface` işlemin neden başarısız olduğunu belirten bir HRESULT.

### <a name="remarks"></a>Açıklamalar

İlk işlev, bu `ComPtr`ile ilişkili arabirime işaretçinin bir kopyasını döndürür. Bu işlev her zaman S_OK döndürür.

İkinci işlev, `QueryInterface` *riıd* parametresi tarafından belirtilen arabirim `ComPtr` için bununla ilişkili arabirim üzerinde bir işlem gerçekleştirir.

Üçüncü işlev, *U* parametresinin `QueryInterface` temel arabirimi `ComPtr` için bununla ilişkili arabirim üzerinde bir işlem gerçekleştirir.

## <a name="detach"></a>ComPtr::D etach

Bu `ComPtr` nesneyi, temsil ettiği arabirimden kaldırır.

```cpp
T* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `ComPtr` nesne tarafından temsil edilen arabirime yönelik bir işaretçi.

## <a name="get"></a>ComPtr:: Get

Bu `ComPtr`ile ilişkili arabirime bir işaretçi alır.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `ComPtr`ile ilişkili arabirime yönelik işaretçi.

## <a name="getaddressof"></a>ComPtr:: GetAddressOf

Bu`ComPtr`tarafından temsil edilen arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bir değişkenin adresi.

## <a name="internaladdref"></a>ComPtr:: InternalAddRef

Bununla ilişkili `ComPtr`arabirimin başvuru sayısını artırır.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="internalrelease"></a>ComPtr:: InternalRelease

Bu `ComPtr`ile ilişkili ARABIRIM üzerinde bir com yayın işlemi gerçekleştirir.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="operator-ampersand"></a>ComPtr:: işleci&amp;

Bu `ComPtr` nesneyle ilişkili arabirimi serbest bırakır ve sonra `ComPtr` nesnenin adresini alır.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtr`bir zayıf başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu yöntemin arabirim işaretçisine bir başvuru yayınlarsa [ComPtr:: GetAddressOf](#getaddressof) öğesinden farklıdır. Arabirim `ComPtr::GetAddressOf` işaretçisinin adresine ihtiyacınız olduğunda, ancak bu arabirimi yayınlamak istemediğinizde kullanın.

## <a name="operator-arrow"></a>ComPtr:: operator-&gt;

Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli şablon türü adı tarafından belirtilen türe yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi, STDMETHOD makrosunu kullanarak oluşan gereksiz yükü kaldırır. Bu işlev yerine `IUnknown` `private`türleriniyapar. `virtual`

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

*LARINIZ*<br/>
Bir sınıf.

*farklı*<br/>
Bir türe veya başka `ComPtr`bir işaretçiye işaretçi, başvuru veya rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtr`bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlecin ilk sürümü geçerli `ComPtr`değere boş bir değer atar.

İkinci sürümde, atama arabirimi işaretçisi geçerli `ComPtr` arabirim işaretçiyle aynı değilse, ikinci arabirim işaretçisi geçerli `ComPtr`olan öğesine atanır.

Üçüncü sürümde, atama arabirimi işaretçisi geçerli `ComPtr`bir öğesine atanır.

Dördüncü sürümde, atama değerinin arabirim işaretçisi geçerli `ComPtr` arabirim işaretçiyle aynı değilse, ikinci arabirim işaretçisi geçerli `ComPtr`öğesine atanır.

Beşinci sürüm bir kopya işleçtir; `ComPtr` geçerli`ComPtr`öğesine bir başvurusu atanır.

Altıncı sürüm, taşıma semantiğini kullanan bir kopya işleçtir; herhangi bir tür statik atama `ComPtr` ise ve sonra geçerli `ComPtr`öğesine atanırsa bir rvalue başvurusu.

Yedinci sürüm, taşıma semantiğini kullanan bir kopya işleçtir; `ComPtr` *U* türünde bir rvalue başvurusu statik bir tür oluşturup geçerli `ComPtr`öğesine atanır.

## <a name="operator-equality"></a>ComPtr:: operator = =

İki `ComPtr` nesnenin eşit olup olmadığını gösterir.

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
Bir `ComPtr` nesneye başvuru.

*b*<br/>
Başka `ComPtr` bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk operatör `true` , nesne *b*nesnesine eşitse, aksi takdirde,. `false`

İkinci ve üçüncü `true` operatörler nesne *a* eşitse `nullptr`, aksi takdirde,. `false`

## <a name="operator-inequality"></a>ComPtr:: operator! =

İki `ComPtr` nesnenin eşit olup olmadığını gösterir.

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
Bir `ComPtr` nesneye başvuru.

*b*<br/>
Başka `ComPtr` bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk operatör `true` , nesne *b*nesnesine eşit değilse, aksi takdirde, `false`olur.

İkinci `true` ve üçüncü operatörler, nesne *a* eşit `nullptr`değilse, aksi takdirde,. `false`

## <a name="operator-microsoft-wrl-details-booltype"></a>ComPtr:: operator Microsoft:: WRL::D euçlar:: BoolType

Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini belirtir.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir arabirim bu `ComPtr`ile ilişkilendirilmişse [BoolStruct:: member](boolstruct-structure.md#member) veri üyesinin adresi; Aksi takdirde, `nullptr`.

## <a name="ptr"></a>ComPtr::p tr_

İle ilişkili arabirime yönelik bir işaretçi içerir ve bu `ComPtr`ile yönetilir.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Açıklamalar

`ptr_`, dahili, korunan bir veri üyesidir.

## <a name="releaseandgetaddressof"></a>ComPtr:: ReleaseAndGetAddressOf

, Bununla ilişkili `ComPtr` arabirimi yayınlar ve sonra yayınlanan arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bunun`ComPtr` [ptr_](#ptr) veri üyesinin adresi.

## <a name="reset"></a>ComPtr:: Reset

İşaretçiyle ilişkili olan arabirime yönelik tüm başvuruları yayınlar `ComPtr`.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Dönüş Değeri

Varsa, yayınlanan başvuruların sayısı.

## <a name="swap"></a>ComPtr:: swap

Geçerli `ComPtr` tarafından yönetilen arabirimi, belirtilen `ComPtr`arabirimiyle yönetilen arabirim ile değiştirir.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>Parametreler

*r*<br/>
A `ComPtr`.

