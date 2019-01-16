---
title: HString Sınıfı
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
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
ms.openlocfilehash: 800ed98656493efc3e0ce59739dab7e4c0bc681f
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335194"
---
# <a name="hstring-class"></a>HString Sınıfı

Ömrünü yönetmek için yardımcı sınıfı bir [HSTRING](/windows/desktop/WinRT/hstring) RAII deseni kullanılarak.

## <a name="syntax"></a>Sözdizimi

```cpp
class HString;
```

## <a name="remarks"></a>Açıklamalar

Windows çalışma zamanı ile dizelere erişim sağlar [HSTRING](/windows/desktop/WinRT/hstring) işler. `HString` Kullanışlı işlevler ve işleçler HSTRING tutamaçları kullanmayı kolaylaştırmak için sınıf sağlar. Bu sınıf, bir RAII deseni sahip HSTRING ömrü başa çıkabilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                | Açıklama
----------------------------------- | -----------------------------------------------------
[HString::HString](#hstring)        | Yeni bir örneğini başlatır `HString` sınıfı.
[HString:: ~ HString](#tilde-hstring) | Geçerli örneğini yok eder `HString` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                     | Açıklama
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString::Attach](#attach)               | Belirtilen ilişkilendirir `HString` geçerli nesneyle `HString` nesne.
[HString::CopyTo](#copyto)               | Geçerli kopyalar `HString` nesnesini bir HSTRING nesnesine.
[HString::Detach](#detach)               | Belirtilen ayırır `HString` nesnesini temel değerinden.
[HString::Get](#get)                     | Temel HSTRING tanıtıcısının değerini alır.
[HString::GetAddressOf](#getaddressof)   | Temel HSTRING tanıtıcısına bir işaretçi alır.
[Hstring::IsValid](#isvalid)             | Belirtir olup olmadığını geçerli `HString` nesne geçerlidir.
[HString::MakeReference](#makereference) | Oluşturur bir `HStringReference` nesnesinden belirtilen dize parametresi.
[HString::Release](#release)             | Temel dize değerini siler ve geçerli başlatır `HString` boş bir değere nesne.
[HString::Set](#set)                     | Geçerli değerini ayarlar `HString` belirtilen geniş karakter dizesini bir nesneye veya `HString` parametresi.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                         | Açıklama
-------------------------------------------- | ----------------------------------------------------------------------------
[HString::operator =](#operator-assign)       | Başka bir değer taşır `HString` geçerli nesneye `HString` nesne.
[HString::operator ==](#operator-equality)    | İki parametrenin eşit olup olmadığını gösterir.
[HString::operator! =](#operator-inequality)  | İki parametrenin eşit olup olmadığını gösterir.
[HString::operator&lt;](#operator-less-than) | İkinci parametre ilk parametre olup değerinden gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HString`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="tilde-hstring"></a>HString:: ~ HString

Geçerli örneğini yok eder `HString` sınıfı.

```cpp
~HString() throw()
```

## <a name="attach"></a>HString::Attach

Belirtilen ilişkilendirir `HString` geçerli nesneyle `HString` nesne.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Parametreler

*HSTR*<br/>
Varolan bir `HString` nesnesi.

## <a name="copyto"></a>HString::CopyTo

Geçerli kopyalar `HString` nesnesini bir HSTRING nesnesine.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Kopyayı alan HSTRING.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [WindowsDuplicateString](https://msdn.microsoft.com/library/br224634.aspx) işlevi.

## <a name="detach"></a>HString::Detach

Belirtilen ayırır `HString` nesnesini temel değerinden.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Arka plandaki `HString` değerden önce ayırma işlemi başlatıldı.

## <a name="get"></a>HString::Get

Temel HSTRING tanıtıcısının değerini alır.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel HSTRING tanıtıcısının değerini

## <a name="getaddressof"></a>HString::GetAddressOf

Temel HSTRING tanıtıcısına bir işaretçi alır.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel HSTRING tanıtıcısına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Temel HSTRING tanıtıcısına dize değerini bu işlemden sonra yok edilir.

## <a name="hstring"></a>HString::HString

Yeni bir örneğini başlatır `HString` sınıfı.

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Parametreler

*HSTR*<br/>
Bir HSTRING tanıtıcısı.

*Diğer*<br/>
Varolan bir `HString` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, yeni bir başlatır `HString` boş olan nesne.

İkinci Oluşturucu, yeni bir başlatır `HString` varolan değerin bir nesneye *diğer* parametresi ve ardından yok eder *diğer* parametresi.

## <a name="isvalid"></a>Hstring::IsValid

Belirtir olup olmadığını geçerli `HString` veya nesne boş.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Parametreler

**doğru** varsa geçerli `HString` nesnesi boş; Aksi takdirde değil **false**.

## <a name="makereference"></a>HString::MakeReference

Oluşturur bir `HStringReference` nesnesinden belirtilen dize parametresi.

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
Hedef boyutunu belirten bir şablon parametresi `HStringReference` arabellek.

*str*<br/>
Bir geniş karakter dizesi bir başvuru.

*Len*<br/>
En büyük uzunluğunu *str* parametre arabelleği bu işlemi kullanmak için. Varsa *len* parametresi belirtilmediyse, tüm *str* parametresi kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Bir `HStringReference` değeri belirtilen türle aynı olan nesne *str* parametresi.

## <a name="operator-assign"></a>HString::operator = işleci

Başka bir değer taşır `HString` geçerli nesneye `HString` nesne.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Varolan bir `HString` nesnesi.

### <a name="remarks"></a>Açıklamalar

Varolan değerin *diğer* nesne geçerli kopyalanır `HString` nesnesi ve ardından *diğer* nesnesi yok edildiğinde.

## <a name="operator-equality"></a>HString::operator == işleci

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

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* olabilir bir `HString` veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

*Sol*<br/>
Karşılaştırılacak ikinci parametre. *sol* olabilir bir `HString` veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* ve *sol* parametreleri eşit; Aksi takdirde **false**.

## <a name="operator-inequality"></a>HString::operator! = işleci

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

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* olabilir bir `HString` veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

*Sol*<br/>
Karşılaştırılacak ikinci parametre. *sol* olabilir bir `HString` veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* ve *sol* parametreleri eşit; Aksi takdirde değil **false**.

## <a name="operator-less-than"></a>HString::operator&lt; işleci

İkinci parametre ilk parametre olup değerinden gösterir.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* başvuru olabilir bir `HString`.

*Sol*<br/>
Karşılaştırılacak ikinci parametre. *Sol* başvuru olabilir bir `HString`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* parametresi değerinden daha küçük *sol* parametre; Aksi takdirde **false**.

## <a name="release"></a>HString::Release

Temel dize değerini siler ve geçerli başlatır `HString` boş bir değere nesne.

```cpp
void Release() throw()
```

## <a name="set"></a>HString::Set

Geçerli değerini ayarlar `HString` belirtilen geniş karakter dizesini bir nesneye veya `HString` parametresi.

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

*str*<br/>
Öğesinin geniş karakterli bir dizedir.

*Len*<br/>
En büyük uzunluğunu *str* geçerli atanan parametresi `HString` nesne.

*HSTR*<br/>
Varolan bir `HString` nesnesi.
