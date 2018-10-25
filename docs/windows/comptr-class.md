---
title: ComPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/01/2018
ms.technology:
- cpp-windows
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9535913bbbeb6ec7e8876acf8254030a7b0611dd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053987"
---
# <a name="comptr-class"></a>ComPtr Sınıfı

Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirlenen arabirimi temsil eden tür. `ComPtr` otomatik olarak temel arabirim işaretçisi için bir başvuru sayısını tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Arabirimi, `ComPtr` temsil eder.

*U*<br/>
Bir sınıfa geçerli `ComPtr` arkadaş olur. (Bu parametre kullanan bir şablonu korunuyor.)

## <a name="remarks"></a>Açıklamalar

`ComPtr<>` temel arabirim işaretçisi temsil eden bir tür bildirir. Kullanma `ComPtr<>` bir değişkeni bildirir ve ardından OK üye erişimi işleci (`->`) bir arabirim üye işlevine erişmek için.

Akıllı işaretçiler hakkında daha fazla bilgi için bkz: "COM akıllı işaretçileri" alt bölümü [COM kodlama uygulamalarını](/windows/desktop/LearnWin32/com-coding-practices) MSDN Kitaplığı'nda konu.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad            | Açıklama
--------------- | ---------------------------------------------------------------
`InterfaceType` | Tarafından belirtilen türe ilişkin bir eşanlam *T* şablon parametresi.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                             | Açıklama
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr::ComPtr](#comptr)        | Yeni bir örneğini başlatır `ComPtr` sınıfı. Varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları aşırı yüklemeler sağlar.
[ComPtr:: ~ ComPtr](#tilde-comptr) | Örneği başlatılmasını geri alır `ComPtr`.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                      | Açıklama
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr::As](#as)                                         | Döndürür bir `ComPtr` belirtilen şablon parametresi tarafından belirlenen arabirimi temsil eden nesne.
[Comptr::asııd](#asiid)                                   | Döndürür bir `ComPtr` belirtilen arabirim kimliği. tarafından belirlenen arabirimi temsil eden nesne
[ComPtr::AsWeak](#asweak)                                 | Geçerli nesnenin zayıf bir başvuru alır.
[ComPtr::Attach](#attach)                                 | Bu ilişkilendirir `ComPtr` geçerli bir şablon türü parametresi tarafından belirtilen arabirim türüne sahip.
[ComPtr::CopyTo](#copyto)                                 | Şununla ilişkili geçerli ya da belirtilen arabirim kopyalar `ComPtr` belirtilen çıkış işaretçi.
[ComPtr::Detach](#detach)                                 | Bu ayırır `ComPtr` arabiriminden temsil eder.
[ComPtr::Get](#get)                                       | Şununla ilişkili arabirim işaretçisi alır `ComPtr`.
[ComPtr::GetAddressOf](#getaddressof)                     | Adresini alır [ptr_](#ptr) bu tarafından temsil edilen arabirimi için bir işaretçi içeren veri üyesi `ComPtr`.
[ComPtr::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Şununla ilişkili arabirimini yayımlar `ComPtr` ve adresini alır. [ptr_](#ptr) yayımlanan arabirimi için bir işaretçi içeren veri üyesi.
[ComPtr::Reset](#reset)                                   | Bununla ilişkili arabirim işaretçisi için tüm başvurularını serbest `ComPtr`.
[ComPtr::Swap](#swap)                                     | Geçerli tarafından yönetilen arabirimi birbiriyle değiştirir `ComPtr` tarafından belirtilen yönetilen arabirimiyle `ComPtr`.

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                        | Açıklama
------------------------------------------- | --------------------------------------------------------------------------------
[Comptr::ınternaladdref](#internaladdref)   | Şununla ilişkili arabiriminin başvuru sayısını artırır `ComPtr`.
[Comptr::ınternalrelease](#internalrelease) | Şununla ilişkili arabirim bir COM yayınında işlemi gerçekleştirir `ComPtr`.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                                                           | Açıklama
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr::operator &](#operator-ampersand)                                                       | Geçerli adresi alır `ComPtr`.
[ComPtr::operator ->](#operator-arrow)                                                          | Geçerli bir şablon parametresi tarafından belirtilen tür için bir işaretçi alır.
[ComPtr::operator =](#operator-assign)                                                          | Geçerli bir değer atar `ComPtr`.
[ComPtr::operator ==](#operator-equality)                                                       | Belirtir olup iki `ComPtr` nesneler.
[ComPtr::operator! =](#operator-inequality)                                                     | Belirtir olup iki `ComPtr` nesneler eşit değildir.
[ComPtr::operator Microsoft::WRL::Details::BoolType](#operator-microsoft-wrl-details-booltype) | Belirtir olup olmadığını bir `ComPtr` bir arabirimin nesne ömrü yönetimi.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                 | Açıklama
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::ptr_](#ptr) | İle ilişkili olan ve bu tarafından yönetilen arabirimi için bir işaretçi içeren `ComPtr`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="tilde-comptr"></a>ComPtr:: ~ ComPtr

Örneği başlatılmasını geri alır `ComPtr`.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>ComPtr::As

Döndürür bir `ComPtr` belirtilen şablon parametresi tarafından belirlenen arabirimi temsil eden nesne.

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
Parametresi tarafından temsil edilmesini arabirimi *p*.

*p*<br/>
A `ComPtr` parametresi tarafından belirtilen arabirim temsil eden nesne *U*. Parametre *p* geçerli entityset'e başvurmadığından `ComPtr` nesne.

### <a name="remarks"></a>Açıklamalar

İlk şablon kodunuzda kullanması gereken biçimidir. İkinci şablonu olduğu gibi C++ dil özellikleri destekleyen bir iç, Yardımcısı özelleştirmesi [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü yazın.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="asiid"></a>Comptr::asııd

Döndürür bir `ComPtr` belirtilen arabirim kimliği. tarafından belirlenen arabirimi temsil eden nesne

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
Bir arabirim kimliği.

*p*<br/>
Nesne Kimliğine eşit bir arabirim varsa *riid*, karakteriyle dolaylı tarafından belirtilen arabirim işaretçisi *riid* parametre; Aksi takdirde, bir işaretçi `IUnknown`.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="asweak"></a>ComPtr::AsWeak

Geçerli nesnenin zayıf bir başvuru alır.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>Parametreler

*pWeakRef*<br/>
Bu işlem tamamlandığında zayıf başvuru nesnesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="attach"></a>ComPtr::Attach

Bu ilişkilendirir `ComPtr` geçerli bir şablon türü parametresi tarafından belirtilen arabirim türüne sahip.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bir arabirim türü.

## <a name="comptr"></a>ComPtr::ComPtr

Yeni bir örneğini başlatır `ComPtr` sınıfı. Varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları aşırı yüklemeler sağlar.

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
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
```

### <a name="parameters"></a>Parametreler

*U*<br/>
Türünü *diğer* parametresi.

*Diğer*<br/>
Bir nesne türü *U*.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu boş bir nesneye hangi insert oluşturur varsayılan oluşturucudur. İkinci oluşturucu belirtir [__nullptr](../windows/nullptr-cpp-component-extensions.md), boş bir nesneye açıkça oluşturulur.

Üçüncü Oluşturucu bir işaretçi tarafından belirtilen nesne bir nesne oluşturur.

Dördüncü ve beşinci oluşturucular kopya oluşturucuları ' dir. Geçerli türüne dönüştürülebilir ise beşinci Oluşturucu nesneyi kopyalar.

Altıncı ve yedinci oluşturucular taşıma oluşturucuları ' dir. Geçerli türüne dönüştürülebilir ise yedinci Oluşturucusu bir nesneyi taşır.

## <a name="copyto"></a>ComPtr::CopyTo

Şununla ilişkili geçerli ya da belirtilen arabirim kopyalar `ComPtr` belirtilen işaretçi.

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
Tür adı.

*ptr*<br/>
Bu işlem tamamlandığında istenen arabirim işaretçisi.

*riid*<br/>
Bir arabirim kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, nedenini belirten bir HRESULT örtük `QueryInterface` işlemi başarısız oldu.

### <a name="remarks"></a>Açıklamalar

İlk işlev, bununla ilişkili arabirimi için bir işaretçi bir kopyasını döndürür. `ComPtr`. Bu işlev her zaman S_OK döndürür.

İkinci işlevi gerçekleştiren bir `QueryInterface` işlemi ile ilişkili arabirimde `ComPtr` tarafından belirtilen arabirim için *riid* parametresi.

Üçüncü işlevi gerçekleştiren bir `QueryInterface` işlemi ile ilişkili arabirimde `ComPtr` temel arabirimi için *U* parametresi.

## <a name="detach"></a>ComPtr::Detach

Bu ayırır `ComPtr` temsil ettiği arabiriminden nesne.

```cpp
T* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bu sunulacağı arabirim işaretçisi `ComPtr` nesne.

## <a name="get"></a>ComPtr::Get

Şununla ilişkili arabirim işaretçisi alır `ComPtr`.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şununla ilişkili arabirim işaretçisi `ComPtr`.

## <a name="getaddressof"></a>ComPtr::GetAddressOf

Adresini alır [ptr_](#ptr) bu tarafından temsil edilen arabirimi için bir işaretçi içeren veri üyesi `ComPtr`.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Bir değişkenin adresidir.

## <a name="internaladdref"></a>Comptr::ınternaladdref

Şununla ilişkili arabiriminin başvuru sayısını artırır `ComPtr`.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="internalrelease"></a>Comptr::ınternalrelease

Şununla ilişkili arabirim bir COM yayınında işlemi gerçekleştirir `ComPtr`.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem korunur.

## <a name="operator-ampersand"></a>ComPtr::operator&amp;

Şununla ilişkili arabirimini yayımlar `ComPtr` nesne ve adresini alır. `ComPtr` nesne.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli zayıf bir başvuru `ComPtr`.

### <a name="remarks"></a>Açıklamalar

Bu yöntem farklıdır [ComPtr::GetAddressOf](#getaddressof) , bu yöntem bir arabirim işaretçisi başvurusu serbest bırakır. Kullanım `ComPtr::GetAddressOf` kullandığınızda arabirim işaretçisi adresini gerektirir ancak bu arabirimi serbest bırakmak istiyor musunuz.

## <a name="operator-arrow"></a>ComPtr::operator-&gt;

Geçerli bir şablon parametresi tarafından belirtilen tür için bir işaretçi alır.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli şablon tür adıyla belirtilen türün işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi, gereksiz yük STDMETHOD makrosu kullanarak neden olunan kaldırır. Bu işlev yapar `IUnknown` türleri `private` yerine `virtual`.

## <a name="operator-assign"></a>ComPtr::operator =

Geçerli bir değer atar `ComPtr`.

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
Bir sınıf.

*Diğer*<br/>
Bir işaretçi, başvuru veya bir tür veya başka bir rvalue başvurusunu `ComPtr`.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru `ComPtr`.

### <a name="remarks"></a>Açıklamalar

Bu işleç ilk sürümü geçerli boş bir değer atar `ComPtr`.

Atama arabirim işaretçisini geçerli aynı değilse, İkinci Sürüm `ComPtr` arabirim işaretçisini, ikinci arabirim işaretçisi için geçerli atandığı `ComPtr`.

Üçüncü sürümünde geçerli atama arabirim işaretçisi atanır `ComPtr`.

Dördüncü sürümünde arabirim işaretçisi atama değerin geçerli aynı değilse `ComPtr` arabirim işaretçisini, ikinci arabirim işaretçisi için geçerli atandığı `ComPtr`.

Bir kopya işleci beşinci sürümüdür; bir başvuru bir `ComPtr` geçerli atanan `ComPtr`.

Taşıma semantiği kullanan bir kopya işlecine altıncı sürümüdür; rvalue başvurusuna bir `ComPtr` herhangi bir tür cast ve ardından geçerli atanan statikse `ComPtr`.

Taşıma semantiği kullanan bir kopya işlecine yedinci sürümüdür; rvalue başvurusuna bir `ComPtr` türü *U* olan statik as ardından ve geçerli atanan `ComPtr`.

## <a name="operator-equality"></a>ComPtr::operator ==

Belirtir olup iki `ComPtr` nesneler.

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
Bir başvuru bir `ComPtr` nesne.

*b*<br/>
Başka bir başvuru `ComPtr` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sayıları **true** , nesne *bir* nesneye eşit olup *b*; Aksi takdirde **false**.

İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşittir **nullptr**; Aksi takdirde **false**.

## <a name="operator-inequality"></a>ComPtr::operator! =

Belirtir olup iki `ComPtr` nesneler eşit değildir.

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
Bir başvuru bir `ComPtr` nesne.

*b*<br/>
Başka bir başvuru `ComPtr` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sayıları **true** , nesne *bir* nesnesine eşit değil *b*; Aksi takdirde **false**.

İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşit değildir **nullptr**; Aksi takdirde **false**.

## <a name="operator-microsoft-wrl-details-booltype"></a>ComPtr::operator Microsoft::WRL::Details::BoolType

Belirtir olup olmadığını bir `ComPtr` bir arabirimin nesne ömrü yönetimi.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir arabirim ile ilişkili ise `ComPtr`, adresini [BoolStruct::Member](../windows/boolstruct-member-data-member.md) veri üyesi; Aksi takdirde **nullptr**.

## <a name="ptr"></a>ComPtr::ptr_

İle ilişkili olan ve bu tarafından yönetilen arabirimi için bir işaretçi içeren `ComPtr`.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Açıklamalar

`ptr_` bir iç ve korumalı veri üyesidir.

## <a name="releaseandgetaddressof"></a>ComPtr::ReleaseAndGetAddressOf

Şununla ilişkili arabirimini yayımlar `ComPtr` ve adresini alır. [ptr_](#ptr) yayımlanan arabirimi için bir işaretçi içeren veri üyesi.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Adresini [ptr_](#ptr) veri üyesi bu `ComPtr`.

## <a name="reset"></a>ComPtr::Reset

Bununla ilişkili arabirim işaretçisi için tüm başvurularını serbest `ComPtr`.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Dönüş Değeri

Varsa, yayımlanan başvuru sayısı.

## <a name="swap"></a>ComPtr::Swap

Geçerli tarafından yönetilen arabirimi birbiriyle değiştirir `ComPtr` tarafından belirtilen yönetilen arabirimiyle `ComPtr`.

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

