---
title: ComPtr Sınıfı
ms.date: 06/02/2020
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
ms.openlocfilehash: 612747fe0acfa29acc3f516f1257e80069d5395c
ms.sourcegitcommit: d695bb727bd2b081af4d50127b0242a9a5bdce61
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84332259"
---
# <a name="comptr-class"></a>ComPtr Sınıfı

Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türü oluşturur. `ComPtr`, temel alınan arabirim işaretçisi için bir başvuru sayısını otomatik olarak tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Temsil eden arabirim `ComPtr` .

*Larınız*<br/>
Geçerli `ComPtr` bir arkadaş olan sınıf. (Bu parametreyi kullanan şablon korunur.)

## <a name="remarks"></a>Açıklamalar

`ComPtr<>`temel alınan arabirim işaretçisini temsil eden bir tür bildirir. `ComPtr<>`Bir değişken bildirmek için kullanın ve ardından `->` bir arabirim üye işlevine erişmek için ok üye erişim işlecini () kullanın.

Akıllı işaretçiler hakkında daha fazla bilgi için MSDN Kitaplığı 'ndaki [com kodlama uygulamaları](/windows/win32/LearnWin32/com-coding-practices) MAKALESININ "com akıllı işaretçiler" alt bölümüne bakın.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Name            | Description
--------------- | ---------------------------------------------------------------
`InterfaceType` | *T* şablonu parametresi tarafından belirtilen tür için eş anlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Name                             | Description
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr:: ComPtr](#comptr)        | `ComPtr` sınıfının yeni bir örneğini başlatır. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.
[ComPtr:: ~ ComPtr](#tilde-comptr) | Bir örneğini kaldırır `ComPtr` .

### <a name="public-methods"></a>Ortak Yöntemler

Name                                                      | Description
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr:: as](#as)                                         | `ComPtr`Belirtilen şablon parametresi tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.
[ComPtr:: AsIID](#asiid)                                   | `ComPtr`Belirtilen ARABIRIM kimliği tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.
[ComPtr:: Aszayıf](#asweak)                                 | Geçerli nesneye zayıf bir başvuru alır.
[ComPtr:: Attach](#attach)                                 | Bunu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirir.
[ComPtr:: CopyTo](#copyto)                                 | Bu ile ilişkili geçerli veya belirtilen arabirimi `ComPtr` belirtilen çıkış işaretçisine kopyalar.
[ComPtr::D etach](#detach)                                 | Bunu `ComPtr` temsil eden arabirimden kaldırır.
[ComPtr:: Get](#get)                                       | Bu ile ilişkili arabirime bir işaretçi alır `ComPtr` .
[ComPtr:: GetAddressOf](#getaddressof)                     | Bu tarafından temsil edilen arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır `ComPtr` .
[ComPtr:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | , Bununla ilişkili arabirimi serbest bırakır `ComPtr` ve sonra serbest olan arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.
[ComPtr::Reset](#reset)                                   | , Bununla ilişkili arabirimi yayınlar `ComPtr` ve yeni başvuru sayısını döndürür.
[ComPtr:: swap](#swap)                                     | Geçerli tarafından yönetilen arabirimi, `ComPtr` belirtilen arabirimiyle yönetilen arabirim ile değiştirir `ComPtr` .

### <a name="protected-methods"></a>Korumalı Yöntemler

Name                                        | Description
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr:: InternalAddRef](#internaladdref)   | Bununla ilişkili arabirimin başvuru sayısını artırır `ComPtr` .
[ComPtr:: InternalRelease](#internalrelease) | Bu ile ilişkili arabirim üzerinde bir COM yayın işlemi gerçekleştirir `ComPtr` .

### <a name="public-operators"></a>Ortak İşleçler

Name                                                                                           | Description
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr:: operator&](#operator-ampersand)                                                       | Geçerli öğesinin adresini alır `ComPtr` .
[ComPtr:: operator->](#operator-arrow)                                                          | Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.
[ComPtr:: operator =](#operator-assign)                                                          | Geçerli bir değer atar `ComPtr` .
[ComPtr:: operator = =](#operator-equality)                                                       | İki nesnenin eşit olup olmadığını gösterir `ComPtr` .
[ComPtr:: operator! =](#operator-inequality)                                                     | İki nesnenin eşit olup olmadığını gösterir `ComPtr` .
[ComPtr:: operator Microsoft:: WRL::D euçlar:: BoolType](#operator-microsoft-wrl-details-booltype) | Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini belirtir.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Name                 | Description
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::p tr_](#ptr) | İle ilişkili arabirime yönelik bir işaretçi içerir ve bu ile yönetilir `ComPtr` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="comptrcomptr"></a><a name="tilde-comptr"></a>ComPtr:: ~ ComPtr

Bir örneğini kaldırır `ComPtr` .

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="comptras"></a><a name="as"></a>ComPtr:: as

`ComPtr`Belirtilen şablon parametresi tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.

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
`ComPtr` *U*parametresi tarafından belirtilen arabirimi temsil eden nesne. *P* parametresi geçerli nesneye başvurmamalıdır `ComPtr` .

### <a name="remarks"></a>Açıklamalar

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon bir dahili, yardımcı özelleşme. [Otomatik](../../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğü gibi C++ dil özelliklerini destekler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="comptrasiid"></a><a name="asiid"></a>ComPtr:: AsIID

`ComPtr`Belirtilen ARABIRIM kimliği tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.

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
Nesnede, KIMLIĞI *riıd*değerine eşit olan bir arabirim varsa, bu değer, *riıd* parametresi tarafından belirtilen arabirime yönelik bir dolaylı olarak dolaylı bir işaretçi. Aksi takdirde, için bir işaretçisi `IUnknown` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="comptrasweak"></a><a name="asweak"></a>ComPtr:: Aszayıf

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

## <a name="comptrattach"></a><a name="attach"></a>ComPtr:: Attach

Bunu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirir.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Bir arabirim türü.

## <a name="comptrcomptr"></a><a name="comptr"></a>ComPtr:: ComPtr

`ComPtr` sınıfının yeni bir örneğini başlatır. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.

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

İlk Oluşturucu, örtük olarak boş bir nesne oluşturan varsayılan oluşturucudur. İkinci Oluşturucu açık bir şekilde boş bir nesne oluşturan [__nullptr](../../extensions/nullptr-cpp-component-extensions.md)belirtir.

Üçüncü Oluşturucu, bir işaretçi tarafından belirtilen nesneden bir nesne oluşturur. ComPtr artık, işaret edilen belleğe sahiptir ve ona bir başvuru sayısı tutar.

Dördüncü ve beşinci oluşturucular kopya oluşturuculardır. Beşinci Oluşturucu geçerli türe dönüştürülebilir bir nesneyi kopyalar.

Altıncı ve yedinci oluşturucular taşıma oluşturuculardır. Yedinci Oluşturucu geçerli türe dönüştürülebilir bir nesneyi taşımaktır.

## <a name="comptrcopyto"></a><a name="copyto"></a>ComPtr:: CopyTo

Bu ile ilişkili geçerli veya belirtilen arabirimi `ComPtr` belirtilen işaretçiye kopyalar.

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

Başarılı olursa S_OK; Aksi takdirde, örtük işlemin neden başarısız olduğunu belirten bir HRESULT `QueryInterface` .

### <a name="remarks"></a>Açıklamalar

İlk işlev, bu ile ilişkili arabirime işaretçinin bir kopyasını döndürür `ComPtr` . Bu işlev her zaman S_OK döndürür.

İkinci işlev, `QueryInterface` `ComPtr` *riıd* parametresi tarafından belirtilen arabirim için bununla ilişkili arabirim üzerinde bir işlem gerçekleştirir.

Üçüncü işlev, `QueryInterface` `ComPtr` *U* parametresinin temel arabirimi için bununla ilişkili arabirim üzerinde bir işlem gerçekleştirir.

## <a name="comptrdetach"></a><a name="detach"></a>ComPtr::D etach

Bu `ComPtr` nesneyi, temsil ettiği arabirimden kaldırır.

```cpp
T* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından temsil edilen arabirime yönelik bir işaretçi `ComPtr` .

## <a name="comptrget"></a><a name="get"></a>ComPtr:: Get

Bu ile ilişkili arabirime bir işaretçi alır `ComPtr` .

```cpp
T* Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu ile ilişkili arabirime yönelik işaretçi `ComPtr` .

## <a name="comptrgetaddressof"></a><a name="getaddressof"></a>ComPtr:: GetAddressOf

Bu tarafından temsil edilen arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır `ComPtr` .

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bir değişkenin adresi.

## <a name="comptrinternaladdref"></a><a name="internaladdref"></a>ComPtr:: InternalAddRef

Bununla ilişkili arabirimin başvuru sayısını artırır `ComPtr` .

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="comptrinternalrelease"></a><a name="internalrelease"></a>ComPtr:: InternalRelease

Bu ile ilişkili arabirim üzerinde bir COM yayın işlemi gerçekleştirir `ComPtr` .

```cpp
unsigned long InternalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="comptroperatoramp"></a><a name="operator-ampersand"></a>ComPtr:: işleci&amp;

Bu nesneyle ilişkili arabirimi serbest bırakır `ComPtr` ve sonra nesnenin adresini alır `ComPtr` .

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir zayıf başvuru `ComPtr` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu yöntemin arabirim işaretçisine bir başvuru yayınlarsa [ComPtr:: GetAddressOf](#getaddressof) öğesinden farklıdır. `ComPtr::GetAddressOf`Arabirim işaretçisinin adresine ihtiyacınız olduğunda, ancak bu arabirimi yayınlamak istemediğinizde kullanın.

## <a name="comptroperator-gt"></a><a name="operator-arrow"></a>ComPtr:: operator-&gt;

Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli şablon türü adı tarafından belirtilen türe yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi, STDMETHOD makrosunu kullanarak oluşan gereksiz yükü kaldırır. Bu işlev `IUnknown` yerine türlerini yapar `private` `virtual` .

## <a name="comptroperator"></a><a name="operator-assign"></a>ComPtr:: operator =

Geçerli bir değer atar `ComPtr` .

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
Bir türe veya başka bir işaretçiye işaretçi, başvuru veya rvalue başvurusu `ComPtr` .

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru `ComPtr` .

### <a name="remarks"></a>Açıklamalar

Bu işlecin ilk sürümü geçerli değere boş bir değer atar `ComPtr` .

İkinci sürümde, atama arabirimi işaretçisi geçerli `ComPtr` arabirim işaretçiyle aynı değilse, ikinci arabirim işaretçisi geçerli öğesine atanır `ComPtr` .

Üçüncü sürümde, atama arabirimi işaretçisi geçerli bir öğesine atanır `ComPtr` .

Dördüncü sürümde, atama değerinin arabirim işaretçisi geçerli `ComPtr` arabirim işaretçiyle aynı değilse, ikinci arabirim işaretçisi geçerli bir değere atanır `ComPtr` .

Beşinci sürüm bir kopya işleçtir; geçerli öğesine bir başvurusu `ComPtr` atanır `ComPtr` .

Altıncı sürüm, taşıma semantiğini kullanan bir kopya işleçtir; `ComPtr`herhangi bir tür statik atama ise ve sonra geçerli öğesine atanırsa bir rvalue başvurusu `ComPtr` .

Yedinci sürüm, taşıma semantiğini kullanan bir kopya işleçtir; U türünde bir rvalue başvurusu `ComPtr` statik bir *U* tür oluşturup geçerli öğesine atanır `ComPtr` .

## <a name="comptroperator"></a><a name="operator-equality"></a>ComPtr:: operator = =

İki nesnenin eşit olup olmadığını gösterir `ComPtr` .

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

*kenarı*<br/>
Başka bir nesneye başvuru `ComPtr` .

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, `true` nesne *b*nesnesine *a* eşitse, aksi takdirde, `false` .

İkinci ve üçüncü operatörler `true` nesne *a* eşitse `nullptr` , aksi takdirde, `false` .

## <a name="comptroperator"></a><a name="operator-inequality"></a>ComPtr:: operator! =

İki nesnenin eşit olup olmadığını gösterir `ComPtr` .

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

*kenarı*<br/>
Başka bir nesneye başvuru `ComPtr` .

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, `true` nesne *b*nesnesine *a* eşit değilse, aksi takdirde, `false` .

İkinci ve üçüncü operatörler `true` nesne *a* eşit değilse `nullptr` , aksi takdirde, `false` .

## <a name="comptroperator-microsoftwrldetailsbooltype"></a><a name="operator-microsoft-wrl-details-booltype"></a>ComPtr:: operator Microsoft:: WRL::D euçlar:: BoolType

Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini belirtir.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir arabirim bu ile ilişkilendirilmişse `ComPtr` [BoolStruct:: member](boolstruct-structure.md#member) veri üyesinin adresi; Aksi takdirde, `nullptr` .

## <a name="comptrptr_"></a><a name="ptr"></a>ComPtr::p tr_

İle ilişkili arabirime yönelik bir işaretçi içerir ve bu ile yönetilir `ComPtr` .

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Açıklamalar

`ptr_`, dahili, korunan bir veri üyesidir.

## <a name="comptrreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtr:: ReleaseAndGetAddressOf

, Bununla ilişkili arabirimi serbest bırakır `ComPtr` ve sonra serbest olan arabirime yönelik bir işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bunun [ptr_](#ptr) veri üyesinin adresi `ComPtr` .

## <a name="comptrreset"></a><a name="reset"></a>ComPtr:: Reset

, Bununla ilişkili arabirimi yayınlar `ComPtr` ve yeni başvuru sayısını döndürür.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Dönüş Değeri

Varsa, temel alınan arabirime kalan başvuruların sayısı.

## <a name="comptrswap"></a><a name="swap"></a>ComPtr:: swap

Geçerli tarafından yönetilen arabirimi, `ComPtr` belirtilen arabirimiyle yönetilen arabirim ile değiştirir `ComPtr` .

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
