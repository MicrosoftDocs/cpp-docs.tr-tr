---
title: HStringReference Sınıfı
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
- corewrappers/Microsoft::WRL::Wrappers::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HStringReference class
- Microsoft::WRL::Wrappers::HStringReference::CopyTo method
- Microsoft::WRL::Wrappers::HStringReference::Get method
- Microsoft::WRL::Wrappers::HStringReference::HStringReference, constructor
- Microsoft::WRL::Wrappers::HStringReference::operator= operator
- Microsoft::WRL::Wrappers::HStringReference::operator== operator
- Microsoft::WRL::Wrappers::HStringReference::operator!= operator
- Microsoft::WRL::Wrappers::HStringReference::operator< operator
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
ms.openlocfilehash: fd064f97081fad1a9df9de0865bb7c46ad5b4484
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371417"
---
# <a name="hstringreference-class"></a>HStringReference Sınıfı

Varolan bir dizeden oluşturulan bir HSTRING'i temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class HStringReference;
```

## <a name="remarks"></a>Açıklamalar

Yeni HSTRING'teki destek arabelleği ömrü Windows Runtime tarafından yönetilmez. Arayan yığın ayırmaönlemek ve bellek sızıntısı riskini ortadan kaldırmak için yığın çerçevesi üzerinde bir kaynak dize ayırır. Ayrıca, arayan, kaynak dize bağlı HSTRING ömrü boyunca değişmeden kalır emin olmalısınız. Daha fazla bilgi için [WindowsCreateStringReference işlevine](/windows/win32/api/winstring/nf-winstring-windowscreatestringreference)bakın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                    | Açıklama
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference::HStringReference](#hstringreference) | `HStringReference` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Üye                              | Açıklama
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | Geçerli `HStringReference` nesneyi bir HSTRING nesnesine kopyalar.
[HStringReference::Get](#get)       | Alttaki HSTRING tutamacının değerini alır.
[HStringReference::GetRawBuffer](#getrawbuffer) | Altta yatan dize verilerine bir işaretçi alır.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                                  | Açıklama
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference::operator=](#operator-assign)       | Başka bir `HStringReference` nesnenin değerini `HStringReference` geçerli nesneye taşır.
[HStringReference::operator==](#operator-equality)    | İki parametrenin eşit olup olmadığını gösterir.
[HStringReference::operator!=](#operator-inequality)  | İki parametrenin eşit olup olmadığını gösterir.
[HStringReference::işleç&lt;](#operator-less-than) | İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HStringReference`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="hstringreferencecopyto"></a><a name="copyto"></a>HStringReference::CopyTo

Geçerli `HStringReference` nesneyi bir HSTRING nesnesine kopyalar.

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

## <a name="hstringreferenceget"></a><a name="get"></a>HStringReference::Get

Alttaki HSTRING tutamacının değerini alır.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel HSTRING tutamacının değeri.

## <a name="hstringreferencegetrawbuffer"></a><a name="getrawbuffer"></a>HStringReference::GetRawBuffer

Altta yatan dize verilerine bir işaretçi alır.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Parametreler

*uzunluk* Verilerin uzunluğunu alan bir **int** değişkenini işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Altta yatan dize verilerine **bir const** işaretçisi.

## <a name="hstringreferencehstringreference"></a><a name="hstringreference"></a>HStringReference::HStringReference

`HStringReference` sınıfının yeni bir örneğini başlatır.

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>Parametreler

*boyutDest*<br/>
Hedef `HStringReference` arabelleğin boyutunu belirten bir şablon parametresi.

*Str*<br/>
Geniş karakterli bir dize için bir başvuru.

*Len*<br/>
Bu işlemde kullanılacak *str* parametre arabelleği maksimum uzunluğu. *Len* parametresi belirtilmemişse, *str* parametresi'nin tamamı kullanılır. *len* boyutdaha *büyükseDest*, *len* *boyutDest*-1 olarak ayarlanır.

*Diğer*<br/>
Başka `HStringReference` bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, parametre `HStringReference` *str*ile aynı boyutta olan yeni bir nesneyi başharfe

İkinci oluşturucu, boyutun `HStringReference` *len*parametreye göre belirttiği yeni bir nesneyi başlarayar.

Üçüncü oluşturucu, `HStringReference` *diğer* parametrenin değerine yeni bir nesne yitirer ve sonra *diğer* parametreyi yok eder.

## <a name="hstringreferenceoperator"></a><a name="operator-assign"></a>HStringReference::operator=

Başka bir `HStringReference` nesnenin değerini `HStringReference` geçerli nesneye taşır.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Varolan bir `HStringReference` nesnesi.

### <a name="remarks"></a>Açıklamalar

Varolan *diğer* nesnenin değeri geçerli `HStringReference` nesneye kopyalanır ve sonra *diğer* nesne yok edilir.

## <a name="hstringreferenceoperator"></a><a name="operator-equality"></a>HStringReference::operator==

İki parametrenin eşit olup olmadığını gösterir.

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* bir `HStringReference` nesne veya HSTRING tutamacı olabilir.

*Rhs*<br/>
Karşılaştırılacak ikinci parametre.  *rhs* bir `HStringReference` nesne veya HSTRING tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

*lhs* ve *rhs* parametreleri eşitse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="hstringreferenceoperator"></a><a name="operator-inequality"></a>HStringReference::operator!=

İki parametrenin eşit olup olmadığını gösterir.

```cpp
inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* bir `HStringReference` nesne veya HSTRING tutamacı olabilir.

*Rhs*<br/>
Karşılaştırılacak ikinci parametre.  *rhs* bir `HStringReference` nesne veya HSTRING tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

*lhs* ve *rhs* parametreleri eşit değilse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="hstringreferenceoperatorlt"></a><a name="operator-less-than"></a>HStringReference::işleç&lt;

İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* bir `HStringReference`referans olabilir .

*Rhs*<br/>
Karşılaştırılacak ikinci parametre.  *rhs* bir `HStringReference`referans olabilir .

### <a name="return-value"></a>Dönüş Değeri

*lhs* parametresi *rhs* parametresinden küçükse **doğrudur;** aksi takdirde, **yanlış**.
