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
ms.openlocfilehash: a3765da94560eb84a1d441a6b25c42822fc857bb
ms.sourcegitcommit: 44eeb065c3148d0484de791080a3f963109744fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79509477"
---
# <a name="hstring-class"></a>HString Sınıfı

Bir [HString 'in, SII](/windows/win32/WinRT/hstring) modelini kullanan yaşam süresini yönetmek için yardımcı bir sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class HString;
```

## <a name="remarks"></a>Açıklamalar

Windows Çalışma Zamanı, [HString](/windows/win32/WinRT/hstring) tanıtıcılarını kullanarak dizelere erişim sağlar. `HString` sınıfı, HSTRING tutamaçlarını kullanarak basitleştirmek için kullanışlı işlevler ve işleçler sağlar. Bu sınıf, bir KORıı düzeniyle sahip olduğu HSTRING 'in ömrünü işleyebilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

Adı                                | Açıklama
----------------------------------- | -----------------------------------------------------
[HString:: HSTRING](#hstring)        | `HString` sınıfının yeni bir örneğini başlatır.
[HString:: ~ HSTRING](#tilde-hstring) | `HString` sınıfının geçerli örneğini yok eder.

### <a name="public-methods"></a>Genel Yöntemler

Adı                                     | Açıklama
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString:: Attach](#attach)               | Belirtilen `HString` nesnesini geçerli `HString` nesnesiyle ilişkilendirir.
[HString:: CopyTo](#copyto)               | Geçerli `HString` nesnesini bir HSTRING nesnesine kopyalar.
[HString::D etach](#detach)               | Belirtilen `HString` nesnesini, temel aldığı değerle kaldırır.
[HString:: Get](#get)                     | Temel alınan HSTRıNG tanıtıcısının değerini alır.
[HString:: GetAddressOf](#getaddressof)   | Temel alınan HSTRıNG tanıtıcısına bir işaretçi alır.
[HSTRING:: GetRawBuffer](#getrawbuffer)   | Temel alınan dize verilerine yönelik bir işaretçi alır.
[HString:: IsValid](#isvalid)             | Geçerli `HString` nesnesinin geçerli olup olmadığını gösterir.
[HString:: MakeReference](#makereference) | Belirtilen dize parametresinden bir `HStringReference` nesnesi oluşturur.
[HString:: Release](#release)             | Temel alınan dize değerini siler ve geçerli `HString` nesnesini boş bir değere ayırır.
[HString:: set](#set)                     | Geçerli `HString` nesnesinin değerini belirtilen geniş karakterli dize veya `HString` parametresine ayarlar.

### <a name="public-operators"></a>Genel İşleçler

Adı                                         | Açıklama
-------------------------------------------- | ----------------------------------------------------------------------------
[HString:: operator =](#operator-assign)       | Başka bir `HString` nesnesinin değerini geçerli `HString` nesnesine kaydırır.
[HString:: operator = =](#operator-equality)    | İki parametrenin eşit olup olmadığını gösterir.
[HString:: operator! =](#operator-inequality)  | İki parametrenin eşit olup olmadığını gösterir.
[HString:: operator&lt;](#operator-less-than) | İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HString`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="tilde-hstring"></a>HString:: ~ HSTRING

`HString` sınıfının geçerli örneğini yok eder.

```cpp
~HString() throw()
```

## <a name="attach"></a>HString:: Attach

Belirtilen `HString` nesnesini geçerli `HString` nesnesiyle ilişkilendirir.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Parametreler

*HSTR*<br/>
Varolan bir `HString` nesnesi.

## <a name="copyto"></a>HString:: CopyTo

Geçerli `HString` nesnesini bir HSTRING nesnesine kopyalar.

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

## <a name="detach"></a>HString::D etach

Belirtilen `HString` nesnesini, temel aldığı değerle kaldırır.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Ayırma işlemi başlatılmadan önce temel alınan `HString` değeri.

## <a name="get"></a>HString:: Get

Temel alınan HSTRıNG tanıtıcısının değerini alır.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan HSTRıNG tanıtıcısının değeri

## <a name="getaddressof"></a>HString:: GetAddressOf

Temel alınan HSTRıNG tanıtıcısına bir işaretçi alır.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan HSTRıNG tanıtıcısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlemden sonra, temeldeki HSTRıNG tanıtıcısının dize değeri yok edilir.

## <a name="getrawbuffer"></a>HSTRING:: GetRawBuffer

Temel alınan dize verilerine yönelik bir işaretçi alır.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Parametreler

*uzunluk* Verilerin uzunluğunu alan bir **int** değişkeninin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Temel alınan dize verilerine yönelik **const** işaretçisi.


## <a name="hstring"></a>HString:: HSTRING

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

İkinci Oluşturucu, var olan *diğer* parametrenin değerine yeni bir `HString` nesnesini başlatır ve ardından *diğer* parametreyi yok eder.

## <a name="isvalid"></a>HString:: IsValid

Geçerli `HString` nesnesinin boş olup olmadığını gösterir.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Parametreler

geçerli `HString` nesnesi boş değilse **true** ; Aksi takdirde, **false**.

## <a name="makereference"></a>HString:: MakeReference

Belirtilen dize parametresinden bir `HStringReference` nesnesi oluşturur.

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
Hedef `HStringReference` arabelleğinin boyutunu belirten bir şablon parametresi.

*üstbilgisine*<br/>
Geniş karakterli bir dizeye başvuru.

*tepe*<br/>
Bu işlemde kullanılacak *Str* parametre arabelleğinin uzunluk üst sınırı. *Len* parametresi belirtilmemişse, *Str* parametresinin tamamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Değeri belirtilen *Str* parametresiyle aynı olan `HStringReference` nesne.

## <a name="operator-assign"></a>HString:: operator = Işleci

Başka bir `HString` nesnesinin değerini geçerli `HString` nesnesine kaydırır.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Varolan bir `HString` nesnesi.

### <a name="remarks"></a>Açıklamalar

Varolan *diğer* nesnenin değeri geçerli `HString` nesnesine kopyalanır ve sonra *diğer* nesne yok edilir.

## <a name="operator-equality"></a>HString:: operator = = Işleci

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
Karşılaştırılacak ilk parametre. *LHS* bir `HString` veya `HStringReference` nesnesi ya da bır HString tutamacı olabilir.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre. *RHS* bir `HString` veya `HStringReference` nesnesi ya da bır HString tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

*LHS* ve *RHS* parametreleri eşitse **true** ; Aksi takdirde, **false**.

## <a name="operator-inequality"></a>HString:: operator! = Işleci

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
Karşılaştırılacak ilk parametre. *LHS* bir `HString` veya `HStringReference` nesnesi ya da bır HString tutamacı olabilir.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre. *RHS* bir `HString` veya `HStringReference` nesnesi ya da bır HString tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

*LHS* ve *RHS* parametreleri eşitse **true** ; Aksi takdirde, **false**.

## <a name="operator-less-than"></a>HString:: operator&lt; Işleci

İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk parametre. *LHS* bir `HString`başvuru olabilir.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre. *RHS* bir `HString`başvuru olabilir.

### <a name="return-value"></a>Dönüş Değeri

*LHS* parametresi *RHS* parametresinden küçükse **true** ; Aksi takdirde, **false**.

## <a name="release"></a>HString:: Release

Temel alınan dize değerini siler ve geçerli `HString` nesnesini boş bir değere ayırır.

```cpp
void Release() throw()
```

## <a name="set"></a>HString:: set

Geçerli `HString` nesnesinin değerini belirtilen geniş karakterli dize veya `HString` parametresine ayarlar.

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
Geçerli `HString` nesnesine atanan *Str* parametresinin en fazla uzunluğu.

*HSTR*<br/>
Varolan bir `HString` nesnesi.
