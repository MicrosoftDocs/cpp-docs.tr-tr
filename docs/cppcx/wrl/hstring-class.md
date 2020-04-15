---
title: HString Sınıfı
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
- corewrappers/Microsoft::WRL::Wrappers::HString::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
- corewrappers/Microsoft::WRL::Wrappers::HString::Release
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
- corewrappers/Microsoft::WRL::Wrappers::HString::~HString
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HString class
- Microsoft::WRL::Wrappers::HString::Attach method
- Microsoft::WRL::Wrappers::HString::CopyTo method
- Microsoft::WRL::Wrappers::HString::Detach method
- Microsoft::WRL::Wrappers::HString::Get method
- Microsoft::WRL::Wrappers::HString::GetAddressOf method
- Microsoft::WRL::Wrappers::HString::HString, constructor
- Microsoft::WRL::Wrappers::HString::IsValid method
- Microsoft::WRL::Wrappers::HString::MakeReference method
- Microsoft::WRL::Wrappers::HString::operator= operator
- Microsoft::WRL::Wrappers::HString::operator== operator
- Microsoft::WRL::Wrappers::HString::operator!= operator
- Microsoft::WRL::Wrappers::HString::operator< operator
- Microsoft::WRL::Wrappers::HString::Release method
- Microsoft::WRL::Wrappers::HString::Set method
- Microsoft::WRL::Wrappers::HString::~HString, destructor
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
ms.openlocfilehash: 625d7b7d6fc001a6fb63144807b5f29d3620485b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371440"
---
# <a name="hstring-class"></a>HString Sınıfı

RAII deseni kullanarak bir [HSTRING'in](/windows/win32/WinRT/hstring) kullanım ömrünü yönetmek için yardımcı sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class HString;
```

## <a name="remarks"></a>Açıklamalar

Windows [Runtime, HSTRING](/windows/win32/WinRT/hstring) tutamaçları aracılığıyla dizeleri erişim sağlar. Sınıf, `HString` HSTRING tutamaçları kullanarak basitleştirmek için kolaylık işlevleri ve işleçler sağlar. Bu sınıf, sahip olduğu HSTRING'in ömrünü bir RAII deseni aracılığıyla işleyebilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                | Açıklama
----------------------------------- | -----------------------------------------------------
[HString::HString](#hstring)        | `HString` sınıfının yeni bir örneğini başlatır.
[HString::~HString](#tilde-hstring) | Sınıfın geçerli örneğini `HString` yok eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                     | Açıklama
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString::Ekle](#attach)               | Belirtilen `HString` nesneyi geçerli `HString` nesneyle ilişkilendirer.
[HString::CopyTo](#copyto)               | Geçerli `HString` nesneyi bir HSTRING nesnesine kopyalar.
[HString::Detach](#detach)               | Belirtilen `HString` nesneyi temel değerinden uzaklaştırın.
[HString::Get](#get)                     | Alttaki HSTRING tutamacının değerini alır.
[HString::GetAddressOf](#getaddressof)   | Altta yatan HSTRING tutamacıiçin bir işaretçi alır.
[HString::GetRawBuffer](#getrawbuffer)   | Altta yatan dize verilerine bir işaretçi alır.
[HString::Geçersiz](#isvalid)             | Geçerli `HString` nesnenin geçerli olup olmadığını gösterir.
[HString::MakeReference](#makereference) | Belirtilen bir `HStringReference` dize parametresinden bir nesne oluşturur.
[HString::Sürüm](#release)             | Temel dize değerini siler ve geçerli `HString` nesneyi boş bir değere intialize eder.
[HString::Set](#set)                     | Geçerli `HString` nesnenin değerini belirtilen geniş karakter dizesine veya `HString` parametreye ayarlar.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                         | Açıklama
-------------------------------------------- | ----------------------------------------------------------------------------
[HString::operator=](#operator-assign)       | Başka bir `HString` nesnenin değerini `HString` geçerli nesneye taşır.
[HString::operator==](#operator-equality)    | İki parametrenin eşit olup olmadığını gösterir.
[HString::işleç!=](#operator-inequality)  | İki parametrenin eşit olup olmadığını gösterir.
[HString::işleç&lt;](#operator-less-than) | İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HString`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="hstringhstring"></a><a name="tilde-hstring"></a>HString::~HString

Sınıfın geçerli örneğini `HString` yok eder.

```cpp
~HString() throw()
```

## <a name="hstringattach"></a><a name="attach"></a>HString::Ekle

Belirtilen `HString` nesneyi geçerli `HString` nesneyle ilişkilendirer.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Parametreler

*hstr*<br/>
Varolan bir `HString` nesnesi.

## <a name="hstringcopyto"></a><a name="copyto"></a>HString::CopyTo

Geçerli `HString` nesneyi bir HSTRING nesnesine kopyalar.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Kopyayı alan HSTRING.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [WindowsDuplicateString](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring) işlevini çağırır.

## <a name="hstringdetach"></a><a name="detach"></a>HString::Detach

Belirtilen `HString` nesneyi temel değerinden uzaklaştırın.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Ayırma `HString` işlemi başlamadan önceki temel değer.

## <a name="hstringget"></a><a name="get"></a>HString::Get

Alttaki HSTRING tutamacının değerini alır.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel HSTRING tutamacının değeri

## <a name="hstringgetaddressof"></a><a name="getaddressof"></a>HString::GetAddressOf

Altta yatan HSTRING tutamacıiçin bir işaretçi alır.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Altta yatan HSTRING tutamacıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlemden sonra, temel HSTRING tutamacının dize değeri yok edilir.

## <a name="hstringgetrawbuffer"></a><a name="getrawbuffer"></a>HString::GetRawBuffer

Altta yatan dize verilerine bir işaretçi alır.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Parametreler

*uzunluk* Verilerin uzunluğunu alan bir **int** değişkenini işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Altta yatan dize verilerine **bir const** işaretçisi.

## <a name="hstringhstring"></a><a name="hstring"></a>HString::HString

`HString` sınıfının yeni bir örneğini başlatır.

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Parametreler

*hstr*<br/>
Bir HSTRING kolu.

*Diğer*<br/>
Varolan bir `HString` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu boş olan `HString` yeni bir nesneyi başharfe alır.

İkinci oluşturucu, varolan `HString` *diğer* parametrenin değerine yeni bir nesne yitirer ve *sonra diğer* parametreyi yok eder.

## <a name="hstringisvalid"></a><a name="isvalid"></a>HString::Geçersiz

Geçerli `HString` nesnenin boş olup olmadığını gösterir.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Parametreler

geçerli `HString` nesne boş değilse **doğru;** aksi takdirde, **yanlış**.

## <a name="hstringmakereference"></a><a name="makereference"></a>HString::MakeReference

Belirtilen bir `HStringReference` dize parametresinden bir nesne oluşturur.

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>Parametreler

*boyutDest*<br/>
Hedef `HStringReference` arabelleğin boyutunu belirten bir şablon parametresi.

*Str*<br/>
Geniş karakterli bir dize için bir başvuru.

*Len*<br/>
Bu işlemde kullanılacak *str* parametre arabelleği maksimum uzunluğu. *Len* parametresi belirtilmemişse, *str* parametresi'nin tamamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Değeri `HStringReference` belirtilen *str* parametresi ile aynı olan bir nesne.

## <a name="hstringoperator-operator"></a><a name="operator-assign"></a>HString::operator= Operatör

Başka bir `HString` nesnenin değerini `HString` geçerli nesneye taşır.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Varolan bir `HString` nesnesi.

### <a name="remarks"></a>Açıklamalar

Varolan *diğer* nesnenin değeri geçerli `HString` nesneye kopyalanır ve sonra *diğer* nesne yok edilir.

## <a name="hstringoperator-operator"></a><a name="operator-equality"></a>HString::operator== Operatör

İki parametrenin eşit olup olmadığını gösterir.

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* bir `HString` veya `HStringReference` nesne veya Bir HSTRING tutamacı olabilir.

*Rhs*<br/>
Karşılaştırılacak ikinci parametre. *rhs* bir `HString` veya `HStringReference` nesne veya Bir HSTRING tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

*lhs* ve *rhs* parametreleri eşitse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="hstringoperator-operator"></a><a name="operator-inequality"></a>HString::operator!= Operatör

İki parametrenin eşit olup olmadığını gösterir.

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* bir `HString` veya `HStringReference` nesne veya Bir HSTRING tutamacı olabilir.

*Rhs*<br/>
Karşılaştırılacak ikinci parametre. *rhs* bir `HString` veya `HStringReference` nesne veya Bir HSTRING tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

*lhs* ve *rhs* parametreleri eşit değilse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="hstringoperatorlt-operator"></a><a name="operator-less-than"></a>HString::operatör&lt; Operatörü

İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* bir `HString`referans olabilir .

*Rhs*<br/>
Karşılaştırılacak ikinci parametre. *rhs* bir `HString`referans olabilir .

### <a name="return-value"></a>Dönüş Değeri

*lhs* parametresi *rhs* parametresinden küçükse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="hstringrelease"></a><a name="release"></a>HString::Sürüm

Temel dize değerini siler ve geçerli `HString` nesneyi boş bir değere intialize eder.

```cpp
void Release() throw()
```

## <a name="hstringset"></a><a name="set"></a>HString::Set

Geçerli `HString` nesnenin değerini belirtilen geniş karakter dizesine veya `HString` parametreye ayarlar.

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Geniş karakterli bir dize.

*Len*<br/>
Geçerli `HString` nesneye atanan *str* parametresinin maksimum uzunluğu.

*hstr*<br/>
Varolan bir `HString` nesnesi.
