---
description: 'Daha fazla bilgi edinin: HStringReference sınıfı'
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
ms.openlocfilehash: d1a45eadd258ba6e17c26cc86aa362011d08ab8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249847"
---
# <a name="hstringreference-class"></a>HStringReference Sınıfı

Varolan bir dizeden oluşturulan bir HSTRıNG temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class HStringReference;
```

## <a name="remarks"></a>Açıklamalar

Yeni HSTRING 'teki yedekleme arabelleğinin yaşam süresi Windows Çalışma Zamanı tarafından yönetilmiyor. Çağıran, yığın ayırmayı önlemek ve bellek sızıntısı riskini ortadan kaldırmak için yığın çerçevesinde bir kaynak dizesi ayırır. Ayrıca çağıran, eklenen HSTRING 'in ömrü boyunca kaynak dizenin değişmeden kalmasını sağlamalıdır. Daha fazla bilgi için bkz. [Windowscreatestringreference işlevi](/windows/win32/api/winstring/nf-winstring-windowscreatestringreference).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                    | Açıklama
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference:: HStringReference](#hstringreference) | `HStringReference` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Üye                              | Açıklama
----------------------------------- | ------------------------------------------------------------------
[HStringReference:: CopyTo](#copyto) | Geçerli `HStringReference` nesneyi BIR HSTRING nesnesine kopyalar.
[HStringReference:: Get](#get)       | Temel alınan HSTRıNG tanıtıcısının değerini alır.
[HStringReference:: GetRawBuffer](#getrawbuffer) | Temel alınan dize verilerine yönelik bir işaretçi alır.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                  | Açıklama
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference:: operator =](#operator-assign)       | Başka bir `HStringReference` nesnenin değerini geçerli `HStringReference` nesneye kaydırır.
[HStringReference:: operator = =](#operator-equality)    | İki parametrenin eşit olup olmadığını gösterir.
[HStringReference:: operator! =](#operator-inequality)  | İki parametrenin eşit olup olmadığını gösterir.
[HStringReference:: işleci&lt;](#operator-less-than) | İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HStringReference`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="hstringreferencecopyto"></a><a name="copyto"></a> HStringReference:: CopyTo

Geçerli `HStringReference` nesneyi BIR HSTRING nesnesine kopyalar.

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

## <a name="hstringreferenceget"></a><a name="get"></a> HStringReference:: Get

Temel alınan HSTRıNG tanıtıcısının değerini alır.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan HSTRıNG tanıtıcısının değeri.

## <a name="hstringreferencegetrawbuffer"></a><a name="getrawbuffer"></a> HStringReference:: GetRawBuffer

Temel alınan dize verilerine yönelik bir işaretçi alır.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Parametreler

*uzunluk* **`int`** Verilerin uzunluğunu alan bir değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

**`const`** Temel alınan dize verilerine yönelik bir işaretçi.

## <a name="hstringreferencehstringreference"></a><a name="hstringreference"></a> HStringReference:: HStringReference

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

*sizeDest*<br/>
Hedef arabelleğin boyutunu belirten bir şablon parametresi `HStringReference` .

*üstbilgisine*<br/>
Geniş karakterli bir dizeye başvuru.

*tepe*<br/>
Bu işlemde kullanılacak *Str* parametre arabelleğinin uzunluk üst sınırı. *Len* parametresi belirtilmemişse, *Str* parametresinin tamamı kullanılır. *Len* , *sizedest* değerinden büyükse, *len* , *sizedest*-1 olarak ayarlanır.

*farklı*<br/>
Başka bir `HStringReference` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `HStringReference` *Str* parametresiyle aynı boyutta olan yeni bir nesne başlatır.

İkinci Oluşturucu, `HStringReference` boyutun parametre *uzunluğu* tarafından belirtilen yeni bir nesnesi başlatır.

Üçüncü Oluşturucu, `HStringReference` *diğer* parametrenin değerine yeni bir nesnesi başlatır ve ardından *diğer* parametreyi yok eder.

## <a name="hstringreferenceoperator"></a><a name="operator-assign"></a> HStringReference:: operator =

Başka bir `HStringReference` nesnenin değerini geçerli `HStringReference` nesneye kaydırır.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Varolan bir `HStringReference` nesnesi.

### <a name="remarks"></a>Açıklamalar

Varolan *diğer* nesnenin değeri geçerli `HStringReference` nesneye kopyalanır ve sonra *diğer* nesne yok edilir.

## <a name="hstringreferenceoperator"></a><a name="operator-equality"></a> HStringReference:: operator = =

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

*Point*<br/>
Karşılaştırılacak ilk parametre. *LHS* bir `HStringReference` nesne veya HString tutamacı olabilir.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre.  *RHS* bir `HStringReference` nesne veya HString tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

**`true`***LHS* ve *RHS* parametreleri eşitse; Aksi takdirde, **`false`** .

## <a name="hstringreferenceoperator"></a><a name="operator-inequality"></a> HStringReference:: operator! =

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

*Point*<br/>
Karşılaştırılacak ilk parametre. *LHS* bir `HStringReference` nesne veya HString tutamacı olabilir.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre.  *RHS* bir `HStringReference` nesne veya HString tutamacı olabilir.

### <a name="return-value"></a>Dönüş Değeri

**`true`***LHS* ve *RHS* parametreleri eşitse; Aksi takdirde, **`false`** .

## <a name="hstringreferenceoperatorlt"></a><a name="operator-less-than"></a> HStringReference:: işleci&lt;

İlk parametrenin ikinci parametreden küçük olup olmadığını gösterir.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk parametre. *LHS* bir başvurusu olabilir `HStringReference` .

*sağ taraftan*<br/>
Karşılaştırılacak ikinci parametre.  *RHS* bir başvurusu olabilir `HStringReference` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***LHS* parametresi *RHS* parametresinden küçükse; Aksi takdirde, **`false`** .
