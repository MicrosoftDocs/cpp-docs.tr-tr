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
ms.openlocfilehash: 549e3fe2a83bb091bcf90e7957b20c219728bdbc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216589"
---
# <a name="hstring-class"></a>HString Sınıfı

Bir [HString 'in, SII](/windows/win32/WinRT/hstring) modelini kullanan yaşam süresini yönetmek için yardımcı bir sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class HString;
```

## <a name="remarks"></a>Açıklamalar

Windows Çalışma Zamanı, [HString](/windows/win32/WinRT/hstring) tanıtıcılarını kullanarak dizelere erişim sağlar. `HString`Sınıfı, HSTRING tutamaçları kullanarak basitleştirecek kullanışlı işlevler ve işleçler sağlar. Bu sınıf, bir KORıı düzeniyle sahip olduğu HSTRING 'in ömrünü işleyebilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                | Açıklama
----------------------------------- | -----------------------------------------------------
[HString:: HSTRING](#hstring)        | `HString` sınıfının yeni bir örneğini başlatır.
[HString:: ~ HSTRING](#tilde-hstring) | Sınıfın geçerli örneğini yok eder `HString` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                     | Açıklama
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString:: Attach](#attach)               | Belirtilen `HString` nesneyi geçerli `HString` nesneyle ilişkilendirir.
[HString:: CopyTo](#copyto)               | Geçerli `HString` nesneyi BIR HSTRING nesnesine kopyalar.
[HString::D etach](#detach)               | Belirtilen `HString` nesneyi, temel aldığı değerle kaldırır.
[HString:: Get](#get)                     | Temel alınan HSTRıNG tanıtıcısının değerini alır.
[HString:: GetAddressOf](#getaddressof)   | Temel alınan HSTRıNG tanıtıcısına bir işaretçi alır.
[HSTRING:: GetRawBuffer](#getrawbuffer)   | Temel alınan dize verilerine yönelik bir işaretçi alır.
[HString:: IsValid](#isvalid)             | Geçerli nesnenin geçerli olup olmadığını gösterir `HString` .
[HString:: MakeReference](#makereference) | `HStringReference`Belirtilen dize parametresinden bir nesne oluşturur.
[HString:: Release](#release)             | Temel alınan dize değerini siler ve geçerli `HString` nesneyi boş bir değere ayırır.
[HString:: set](#set)                     | Geçerli `HString` nesnenin değerini belirtilen geniş karakterli dize veya `HString` parametreye ayarlar.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                         | Açıklama
-------------------------------------------- | ----------------------------------------------------------------------------
[HString:: operator =](#operator-assign)       | Başka bir `HString` nesnenin değerini geçerli `HString` nesneye kaydırır.
[HString:: operator = =](#operator-equality)    | İki parametrenin eşit olup olmadığını gösterir.
[HString:: operator! =](#operator-inequality)  | İki parametrenin eşit olup olmadığını gösterir.
[HString:: işleci&lt;](#operator-less-than) | İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HString`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="hstringhstring"></a><a name="tilde-hstring"></a>HString:: ~ HSTRING

Sınıfın geçerli örneğini yok eder `HString` .

```cpp
~HString() throw()
```

## <a name="hstringattach"></a><a name="attach"></a>HString:: Attach

Belirtilen `HString` nesneyi geçerli `HString` nesneyle ilişkilendirir.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Parametreler

*HSTR*<br/>
Varolan bir `HString` nesnesi.

## <a name="hstringcopyto"></a><a name="copyto"></a>HString:: CopyTo

Geçerli `HString` nesneyi BIR HSTRING nesnesine kopyalar.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Kopyayı alan HSTRıNG.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [WindowsDuplicateString](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring) işlevini çağırır.

## <a name="hstringdetach"></a><a name="detach"></a>HString::D etach

Belirtilen `HString` nesneyi, temel aldığı değerle kaldırır.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Dönüş Değeri

`HString`Ayırma işlemi başlatılmadan önce temel alınan değer.

## <a name="hstringget"></a><a name="get"></a>HString:: Get

Temel alınan HSTRıNG tanıtıcısının değerini alır.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan HSTRıNG tanıtıcısının değeri

## <a name="hstringgetaddressof"></a><a name="getaddressof"></a>HString:: GetAddressOf

Temel alınan HSTRıNG tanıtıcısına bir işaretçi alır.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan HSTRıNG tanıtıcısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlemden sonra, temeldeki HSTRıNG tanıtıcısının dize değeri yok edilir.

## <a name="hstringgetrawbuffer"></a><a name="getrawbuffer"></a>HSTRING:: GetRawBuffer

Temel alınan dize verilerine yönelik bir işaretçi alır.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Parametreler

*uzunluk* **`int`** Verilerin uzunluğunu alan bir değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

**`const`** Temel alınan dize verilerine yönelik bir işaretçi.

## <a name="hstringhstring"></a><a name="hstring"></a>HString:: HSTRING

`HString` sınıfının yeni bir örneğini başlatır.

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Parametreler

*HSTR*<br/>
Bir HSTRıNG tanıtıcısı.

*farklı*<br/>
Varolan bir `HString` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu boş olan yeni bir `HString` nesnesi başlatır.

İkinci Oluşturucu, `HString` var olan *diğer* parametrenin değerine yeni bir nesnesi başlatır ve ardından *diğer* parametreyi yok eder.

## <a name="hstringisvalid"></a><a name="isvalid"></a>HString:: IsValid

Geçerli nesnenin boş olup olmadığını gösterir `HString` .

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Parametreler

**`true`** geçerli `HString` nesne boş değilse, tersi durumda **`false`** .

## <a name="hstringmakereference"></a><a name="makereference"></a>HString:: MakeReference

`HStringReference`Belirtilen dize parametresinden bir nesne oluşturur.

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

*sizeDest*<br/>
Hedef arabelleğin boyutunu belirten bir şablon parametresi `HStringReference` .

*üstbilgisine*<br/>
Geniş karakterli bir dizeye başvuru.

*tepe*<br/>
Bu işlemde kullanılacak *Str* parametre arabelleğinin uzunluk üst sınırı. *Len* parametresi belirtilmemişse, *Str* parametresinin tamamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

`HStringReference`Değeri belirtilen *Str* parametresiyle aynı olan bir nesne.

## <a name="hstringoperator-operator"></a><a name="operator-assign"></a>HString:: operator = Işleci

Başka bir `HString` nesnenin değerini geçerli `HString` nesneye kaydırır.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Varolan bir `HString` nesnesi.

### <a name="remarks"></a>Açıklamalar

Varolan *diğer* nesnenin değeri geçerli `HString` nesneye kopyalanır ve sonra *diğer* nesne yok edilir.

## <a name="hstringoperator-operator"></a><a name="operator-equality"></a>HString:: operator = = Işleci

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

*Point*<br/>
Karşılaştırılacak ilk parametre. *LHS* bir `HString` veya `HStringReference` NESNESI ya da bir HString tutamacı olabilir.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre. *RHS* bir `HString` veya `HStringReference` NESNESI ya da bir HString tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

**`true`***LHS* ve *RHS* parametreleri eşitse; Aksi takdirde, **`false`** .

## <a name="hstringoperator-operator"></a><a name="operator-inequality"></a>HString:: operator! = Işleci

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

*Point*<br/>
Karşılaştırılacak ilk parametre. *LHS* bir `HString` veya `HStringReference` NESNESI ya da bir HString tutamacı olabilir.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre. *RHS* bir `HString` veya `HStringReference` NESNESI ya da bir HString tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

**`true`***LHS* ve *RHS* parametreleri eşitse; Aksi takdirde, **`false`** .

## <a name="hstringoperatorlt-operator"></a><a name="operator-less-than"></a>HString:: operator &lt; işleci

İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk parametre. *LHS* bir başvurusu olabilir `HString` .

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre. *RHS* bir başvurusu olabilir `HString` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***LHS* parametresi *RHS* parametresinden küçükse; Aksi takdirde, **`false`** .

## <a name="hstringrelease"></a><a name="release"></a>HString:: Release

Temel alınan dize değerini siler ve geçerli `HString` nesneyi boş bir değere ayırır.

```cpp
void Release() throw()
```

## <a name="hstringset"></a><a name="set"></a>HString:: set

Geçerli `HString` nesnenin değerini belirtilen geniş karakterli dize veya `HString` parametreye ayarlar.

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

*üstbilgisine*<br/>
Geniş karakterli bir dize.

*tepe*<br/>
Geçerli nesneye atanan *Str* parametresinin en fazla uzunluğu `HString` .

*HSTR*<br/>
Varolan bir `HString` nesnesi.
