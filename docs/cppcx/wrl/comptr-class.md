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
ms.openlocfilehash: 89c09ede972f5bdd5da1dde810cad31733bdf338
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372649"
---
# <a name="comptr-class"></a>ComPtr Sınıfı

Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı işaretçi* türü oluşturur. `ComPtr`otomatik olarak temel arabirim işaretçisi için bir başvuru sayısı tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Temsil ettiği `ComPtr` arabirim.

*U*<br/>
Akımın `ComPtr` arkadaş olduğu bir sınıf. (Bu parametreyi kullanan şablon korunur.)

## <a name="remarks"></a>Açıklamalar

`ComPtr<>`alttaki arabirim işaretçisini temsil eden bir tür bildirir. Bir `ComPtr<>` değişkeni bildirmek ve sonra bir arabirim`->`üye işlevine erişmek için ok üye erişim işleci () kullanın.

Akıllı işaretçiler hakkında daha fazla bilgi için, MSDN Kitaplığı'ndaki [COM Kodlama Uygulamaları](/windows/win32/LearnWin32/com-coding-practices) konusunun "COM Akıllı İşaretçileri" alt bölümüne bakın.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı            | Açıklama
--------------- | ---------------------------------------------------------------
`InterfaceType` | *T* şablonu parametresi tarafından belirtilen türiçin eşanlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                             | Açıklama
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[İşlem::ComPtr](#comptr)        | Sınıfın yeni bir örneğini `ComPtr` intialize eder. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.
[ComPtr::~ComPtr](#tilde-comptr) | Bir örneğini `ComPtr`deinitialize eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                      | Açıklama
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr::As](#as)                                         | Belirtilen `ComPtr` şablon parametresi tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.
[ComPtr::AsIID](#asiid)                                   | Belirtilen `ComPtr` arabirim kimliği yle tanımlanan arabirimi temsil eden bir nesne döndürür.
[ComPtr::AsWeak](#asweak)                                 | Geçerli nesneye zayıf bir başvuru alır.
[ComPtr::Ekle](#attach)                                 | Bunu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirer.
[ComPtr::CopyTo](#copyto)                                 | Bu `ComPtr` durumla ilişkili geçerli veya belirtilen arabirimi belirtilen çıktı işaretçisine kopyalar.
[ComPtr::Detach](#detach)                                 | Bunu `ComPtr` temsil ettiği arabirimden uzaklaştırın.
[ComPtr::Get](#get)                                       | Bununla `ComPtr`ilişkili arabirimin işaretçisini alır.
[ComPtr::GetAddressOf](#getaddressof)                     | Bu tarafından temsil edilen arabirime işaretçisi içeren [ptr_](#ptr) `ComPtr`veri üyesinin adresini alır.
[ComPtr::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Bununla `ComPtr` ilişkili arabirimi serbest bırakır ve ardından serbest bırakılan arabirime işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.
[ComPtr::Reset](#reset)                                   | İşaretçi için tüm başvuruları bu `ComPtr`ile ilişkili arabirime verir.
[ComPtr::Takas](#swap)                                     | Değiştirilen arabirim tarafından yönetilen `ComPtr` arayüz ile akım `ComPtr`tarafından yönetilen arayüz belirtilen.

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                        | Açıklama
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr::InternalAddRef](#internaladdref)   | Bu `ComPtr`ile ilişkili arabirimin başvuru sayısını artışlar.
[ComPtr::InternalRelease](#internalrelease) | Bununla `ComPtr`ilişkili arabirimde bir COM Release işlemi gerçekleştirir.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                                                                           | Açıklama
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr::operatör&](#operator-ampersand)                                                       | Geçerli `ComPtr`adresi alır.
[ComPtr::operatör->](#operator-arrow)                                                          | Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.
[ComPtr::operator=](#operator-assign)                                                          | Geçerli `ComPtr`değer atar.
[ComPtr::operator==](#operator-equality)                                                       | İki nesnenin `ComPtr` eşit olup olmadığını gösterir.
[ComPtr::operatör!=](#operator-inequality)                                                     | İki nesnenin `ComPtr` eşit olup olmadığını gösterir.
[ComPtr::operatör Microsoft::WRL::Details::BoolType](#operator-microsoft-wrl-details-booltype) | A'nın `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini gösterir.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                 | Açıklama
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::ptr_](#ptr) | Bu `ComPtr`ile ilişkili ve yönetilen arabirim için bir işaretçi içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** client.h

**Ad alanı:** Microsoft::WRL

## <a name="comptrcomptr"></a><a name="tilde-comptr"></a>ComPtr::~ComPtr

Bir örneğini `ComPtr`deinitialize eder.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="comptras"></a><a name="as"></a>ComPtr::As

Belirtilen `ComPtr` şablon parametresi tarafından tanımlanan arabirimi temsil eden bir nesne döndürür.

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

*U*<br/>
Arabirim *parametre p*ile temsil edilecek .

*P*<br/>
U `ComPtr` parametresi tarafından belirtilen *U*arabirimi temsil eden bir nesne. Parametre *p* geçerli `ComPtr` nesneye başvurmamalıdır.

### <a name="remarks"></a>Açıklamalar

İlk şablon, kodunuzda kullanmanız gereken formdur. İkinci şablon, [otomatik](../../cpp/auto-cpp.md) tür tümdengelimi anahtar sözcüğü gibi C++ dil özelliklerini destekleyen dahili, yardımcı uzmanlıktır.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="comptrasiid"></a><a name="asiid"></a>ComPtr::AsIID

Belirtilen `ComPtr` arabirim kimliği yle tanımlanan arabirimi temsil eden bir nesne döndürür.

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arayüz kimliği.

*P*<br/>
Nesnenin kimliği *riid'e*eşit bir arabirime sahipse, *riid* parametresi tarafından belirtilen arabirime iki kat daha dolaylı işaretçi; aksi takdirde, `IUnknown`bir işaretçi .

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="comptrasweak"></a><a name="asweak"></a>ComPtr::AsWeak

Geçerli nesneye zayıf bir başvuru alır.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>Parametreler

*pWeakRef*<br/>
Bu işlem tamamlandığında, zayıf bir başvuru nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="comptrattach"></a><a name="attach"></a>ComPtr::Ekle

Bunu `ComPtr` geçerli şablon türü parametresi tarafından belirtilen arabirim türüyle ilişkilendirer.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Arayüz türü.

## <a name="comptrcomptr"></a><a name="comptr"></a>İşlem::ComPtr

Sınıfın yeni bir örneğini `ComPtr` intialize eder. Aşırı yüklemeler varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.

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

*U*<br/>
*Diğer* parametrenin türü.

*Diğer*<br/>
*U*türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, açık bir nesne oluşturan varsayılan oluşturucudur. İkinci oluşturucu, boş bir nesne yi açıkça oluşturan [__nullptr](../../extensions/nullptr-cpp-component-extensions.md)belirtir.

Üçüncü oluşturucu bir işaretçi tarafından belirtilen nesneden bir nesne oluşturur. ComPtr artık işaretli belleğe sahip ve ona bir başvuru sayısı tutar.

Dördüncü ve beşinci yapıcılar kopya yapıcılardır. Beşinci oluşturucu, geçerli türe dönüştürülebilirse nesneyi kopyalar.

Altıncı ve yedinci yapıcılar hareket yapıcılarıdır. Yedinci oluşturucu, geçerli türe dönüştürülebilir sayılsa bir nesneyi taşır.

## <a name="comptrcopyto"></a><a name="copyto"></a>ComPtr::CopyTo

Bu `ComPtr` durumla ilişkili geçerli veya belirtilen arabirimi belirtilen işaretçiye kopyalar.

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

*U*<br/>
Bir tür adı.

*Ptr*<br/>
Bu işlem tamamlandığında, istenen arabirime işaretçi.

*Riid*<br/>
Arayüz kimliği.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, örtük `QueryInterface` işlemin neden başarısız olduğunu gösteren bir HRESULT olur.

### <a name="remarks"></a>Açıklamalar

İlk işlev, bir işaretçinin bir kopyasını `ComPtr`bu ile ilişkili arabirime döndürür. Bu işlev her zaman S_OK döndürür.

İkinci *işlev, riid* parametresi `ComPtr` tarafından belirtilen arabirim için bununla ilişkili arabirimde bir `QueryInterface` işlem gerçekleştirir.

Üçüncü *işlev,* `QueryInterface` U parametresinin temel arabirimi için bununla `ComPtr` ilişkili arabirimde bir işlem gerçekleştirir.

## <a name="comptrdetach"></a><a name="detach"></a>ComPtr::Detach

Bu `ComPtr` nesneyi temsil ettiği arabirimden uzaklaştırın.

```cpp
T* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `ComPtr` nesne tarafından temsil edilen arabirimin işaretçisi.

## <a name="comptrget"></a><a name="get"></a>ComPtr::Get

Bununla `ComPtr`ilişkili arabirimin işaretçisini alır.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bununla `ComPtr`ilişkili arabirimi işaretçi.

## <a name="comptrgetaddressof"></a><a name="getaddressof"></a>ComPtr::GetAddressOf

Bu tarafından temsil edilen arabirime işaretçisi içeren [ptr_](#ptr) `ComPtr`veri üyesinin adresini alır.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bir değişkenin adresi.

## <a name="comptrinternaladdref"></a><a name="internaladdref"></a>ComPtr::InternalAddRef

Bu `ComPtr`ile ilişkili arabirimin başvuru sayısını artışlar.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="comptrinternalrelease"></a><a name="internalrelease"></a>ComPtr::InternalRelease

Bununla `ComPtr`ilişkili arabirimde bir COM Release işlemi gerçekleştirir.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="comptroperatoramp"></a><a name="operator-ampersand"></a>ComPtr::operatör&amp;

Bu `ComPtr` nesneyle ilişkili arabirimi serbest bırakır ve `ComPtr` nesnenin adresini alır.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtr`zayıf bir başvuru .

### <a name="remarks"></a>Açıklamalar

Bu yöntem [ComPtr farklıdır::GetAddressOf](#getaddressof) bu yöntem arabirim işaretçisi için bir başvuru bültenleri. Arabirim işaretçisinin adresini istediğinizde ancak bu arabirimi serbest bırakmak istemediğiniz zaman kullanın. `ComPtr::GetAddressOf`

## <a name="comptroperator-gt"></a><a name="operator-arrow"></a>ComPtr::operatör-&gt;

Geçerli şablon parametresi tarafından belirtilen türe bir işaretçi alır.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli şablon türü adı tarafından belirtilen türü işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev, STDMETHOD makrosu kullanılarak kaynaklanan gereksiz yükü kaldırır. Bu `IUnknown` işlev, `private` `virtual`'' yerine türleri yapar.

## <a name="comptroperator"></a><a name="operator-assign"></a>ComPtr::operator=

Geçerli `ComPtr`değer atar.

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

*U*<br/>
Bir ders.

*Diğer*<br/>
Bir türe veya başka `ComPtr`bir türe bir işaretçi, başvuru veya rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtr`bir başvuru .

### <a name="remarks"></a>Açıklamalar

Bu işlecinin ilk sürümü geçerli `ComPtr`boş bir değer atar.

İkinci sürümde, atanan arabirim işaretçisi geçerli `ComPtr` arabirim işaretçisi ile aynı `ComPtr`değilse, ikinci arabirim işaretçisi geçerli ye atanır.

Üçüncü sürümde, atanan arabirim işaretçisi `ComPtr`geçerli .

Dördüncü sürümde, atanan değerin arabirim işaretçisi geçerli `ComPtr` arabirim işaretçisi ile aynı `ComPtr`değilse, ikinci arabirim işaretçisi geçerli ye atanır.

Beşinci sürüm bir kopya işlecidir; a `ComPtr` başvurusu geçerliye `ComPtr`atanır.

Altıncı sürüm, hareket semantikleri kullanan bir kopya işlecidir; herhangi bir tür `ComPtr` statik döküm ise bir rvalue başvuru `ComPtr`ve daha sonra geçerli atanmıştır .

Yedinci sürüm, hareket semantikleri kullanan bir kopya işlecidir; *U* türüne bir `ComPtr` rvalue başvurusu statik döküm sonra `ComPtr`ve geçerli .

## <a name="comptroperator"></a><a name="operator-equality"></a>ComPtr::operator==

İki nesnenin `ComPtr` eşit olup olmadığını gösterir.

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

*A*<br/>
Bir `ComPtr` nesneye başvuru.

*B*<br/>
Başka bir `ComPtr` nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

*A* nesnesi `true` *b*nesnesine eşitse ilk işleç verir; aksi `false`takdirde, .

A nesnesi `true` eşitse *a* `nullptr`ikinci ve üçüncü işleçler verim; aksi `false`takdirde, .

## <a name="comptroperator"></a><a name="operator-inequality"></a>ComPtr::operatör!=

İki nesnenin `ComPtr` eşit olup olmadığını gösterir.

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

*A*<br/>
Bir `ComPtr` nesneye başvuru.

*B*<br/>
Başka bir `ComPtr` nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

*A* nesnesi `true` *b*nesnesine eşit değilse ilk işleç verir; aksi `false`takdirde, .

A nesnesi `true` eşit *a* değilse ikinci ve üçüncü işleçler `nullptr`verim; aksi `false`takdirde, .

## <a name="comptroperator-microsoftwrldetailsbooltype"></a><a name="operator-microsoft-wrl-details-booltype"></a>ComPtr::operatör Microsoft::WRL::Details::BoolType

A'nın `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini gösterir.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir arabirim bununla `ComPtr`ilişkiliyse, [BoolStruct adresi::Üye](boolstruct-structure.md#member) veri üyesi; aksi `nullptr`takdirde, .

## <a name="comptrptr_"></a><a name="ptr"></a>ComPtr::ptr_

Bu `ComPtr`ile ilişkili ve yönetilen arabirim için bir işaretçi içerir.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Açıklamalar

`ptr_`dahili, korumalı bir veri üyesidir.

## <a name="comptrreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtr::ReleaseAndGetAddressOf

Bununla `ComPtr` ilişkili arabirimi serbest bırakır ve ardından serbest bırakılan arabirime işaretçi içeren [ptr_](#ptr) veri üyesinin adresini alır.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bunun [ptr_](#ptr) veri üyesinin `ComPtr`adresi.

## <a name="comptrreset"></a><a name="reset"></a>ComPtr::Sıfırlama

İşaretçi için tüm başvuruları bu `ComPtr`ile ilişkili arabirime verir.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Dönüş Değeri

Varsa yayımlanan başvuru sayısı.

## <a name="comptrswap"></a><a name="swap"></a>ComPtr::Takas

Değiştirilen arabirim tarafından yönetilen `ComPtr` arayüz ile akım `ComPtr`tarafından yönetilen arayüz belirtilen.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>Parametreler

*R*<br/>
Bir `ComPtr`.
