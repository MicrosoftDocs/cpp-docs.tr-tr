---
title: HStringReference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4754a74365b2c596e240bd13eb11fdc852205e2c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077898"
---
# <a name="hstringreference-class"></a>HStringReference Sınıfı

Varolan bir dizeden oluşturulan bir HSTRING temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class HStringReference;
```

## <a name="remarks"></a>Açıklamalar

Yeni HSTRING öğesindeki yedekleme arabelleğinin yaşam süresi Windows çalışma zamanı tarafından yönetilmiyor. Arayanın yığın ayırmasını engellemek ve bellek sızıntısı riskini ortadan kaldırmak için yığın çerçevesinde bir kaynak dizesi ayırır. Ayrıca, arayanın eklenen HSTRING ömrü boyunca kaynak dizesi değişmeden kalır emin olmalısınız. Daha fazla bilgi için [WindowsCreateStringReference işlevi](/windows/desktop/api/winstring/nf-winstring-windowscreatestringreference).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                    | Açıklama
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference::HStringReference](#hstringreference) | Yeni bir örneğini başlatır `HStringReference` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Üye                              | Açıklama
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | Geçerli kopyalar `HStringReference` nesnesini bir HSTRING nesnesine.
[HStringReference::Get](#get)       | Temel HSTRING tanıtıcısının değerini alır.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                  | Açıklama
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference::operator =](#operator-assign)       | Başka bir değer taşır `HStringReference` geçerli nesneye `HStringReference` nesne.
[HStringReference::operator ==](#operator-equality)    | İki parametrenin eşit olup olmadığını gösterir.
[HStringReference::operator! =](#operator-inequality)  | İki parametrenin eşit olup olmadığını gösterir.
[HStringReference::operator&lt;](#operator-less-than) | İkinci parametre ilk parametre olup değerinden gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HStringReference`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="copyto"></a>HStringReference::CopyTo

Geçerli kopyalar `HStringReference` nesnesini bir HSTRING nesnesine.

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

## <a name="get"></a>HStringReference::Get

Temel HSTRING tanıtıcısının değerini alır.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Dönüş Değeri

Temel HSTRING tanıtıcısının değerini.

## <a name="hstringreference"></a>HStringReference::HStringReference

Yeni bir örneğini başlatır `HStringReference` sınıfı.

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
Hedef boyutunu belirten bir şablon parametresi `HStringReference` arabellek.

*str*<br/>
Bir geniş karakter dizesi bir başvuru.

*Len*<br/>
En büyük uzunluğunu *str* parametre arabelleği bu işlemi kullanmak için. Varsa *len* parametresi belirtilmediyse, tüm *str* parametresi kullanılır. Varsa *len* büyüktür *sizeDest*, *len* ayarlanır *sizeDest*-1.

*Diğer*<br/>
Başka bir `HStringReference` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, yeni bir başlatır `HStringReference` aynı boyuttaki parametre olarak nesne *str*.

İkinci Oluşturucu, yeni bir başlatır `HStringReference` nesnesinin boyutu specifeid parametresi tarafından *len*.

Üçüncü Oluşturucu, yeni bir başlatır `HStringReference` değerini nesnesine *diğer* parametresi ve ardından yok eder *diğer* parametresi.

## <a name="operator-assign"></a>HStringReference::operator =

Başka bir değer taşır `HStringReference` geçerli nesneye `HStringReference` nesne.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Varolan bir `HStringReference` nesnesi.

### <a name="remarks"></a>Açıklamalar

Varolan değerin *diğer* nesne geçerli kopyalanır `HStringReference` nesnesi ve ardından *diğer* nesnesi yok edildiğinde.

## <a name="operator-equality"></a>HStringReference::operator ==

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

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* olabilir bir `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

*Sol*<br/>
Karşılaştırılacak ikinci parametre.  *Sol* olabilir bir `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* ve *sol* parametreleri eşit; Aksi takdirde **false**.

## <a name="operator-inequality"></a>HStringReference::operator! =

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

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* olabilir bir `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

*Sol*<br/>
Karşılaştırılacak ikinci parametre.  *Sol* olabilir bir `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* ve *sol* parametreleri eşit; Aksi takdirde değil **false**.

## <a name="operator-less-than"></a>HStringReference::operator&lt;

İkinci parametre ilk parametre olup değerinden gösterir.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* başvuru olabilir bir `HStringReference`.

*Sol*<br/>
Karşılaştırılacak ikinci parametre.  *Sol* başvuru olabilir bir `HStringReference`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* parametresi değerinden daha küçük *sol* parametre; Aksi takdirde **false**.
