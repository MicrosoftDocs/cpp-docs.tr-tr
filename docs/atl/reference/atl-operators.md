---
title: ATL İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 8c15daa1d2b12c58323ef5ef75559a2ab911ad93
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319231"
---
# <a name="atl-operators"></a>ATL İşleçleri

Bu bölümde ATL global operatörleri için başvuru konuları yer almaktadır.

|İşleç|Açıklama|
|--------------|-----------------|
|[işleç ==](#operator_eq_eq)|Eşitlik için `CSid` iki `SID` nesneyi veya yapıyı karşılaştırır.|
|[işleç !=](#operator_neq)|Eşitsizlik için `CSid` iki `SID` nesneyi veya yapıları karşılaştırır.|
|[operatör <](#operator_lt)|İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ `CSid` taraftaki nesne veya `SID` yapıdan daha az olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).|
|[operatör >](#operator_gt)|İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ `CSid` taraftaki nesne veya `SID` yapıdan büyük olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).|
|[operatör <=](#operator_lt__eq)|İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ taraftaki `CSid` nesne `SID` veya yapıdan daha az veya eşit olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).|
|[operatör >=](#operator_gt__eq)|İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ taraftaki `CSid` nesne `SID` veya yapıdan büyük veya eşit olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h.

## <a name="operator-"></a><a name="operator_eq_eq"></a>işleç ==

Eşitlik `CSid` için nesneleri `SID` veya (güvenlik tanımlayıcısı) yapılarını karşılaştırır.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak `CSid` ilk `SID` nesne veya yapı.

*Rhs*<br/>
Karşılaştırılacak `CSid` ikinci `SID` nesne veya yapı.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse DOĞRU, eşit değilse FALSE döndürür.

## <a name="operator-"></a><a name="operator_neq"></a>işleç !=

`CSid` Eşitsizlik için nesneleri `SID` veya (güvenlik tanımlayıcısı) yapıları karşılaştırır.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak `CSid` ilk `SID` nesne veya yapı.

*Rhs*<br/>
Karşılaştırılacak `CSid` ikinci `SID` nesne veya yapı.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşit değilse DOĞRU, eşitse FALSE döndürür.

## <a name="operator-"></a><a name="operator_lt"></a>operatör <

İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ `CSid` taraftaki nesne veya `SID` yapıdan daha az olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak `CSid` ilk `SID` nesne veya yapı.

*Rhs*<br/>
Karşılaştırılacak `CSid` ikinci `SID` nesne veya yapı.

### <a name="return-value"></a>Dönüş Değeri

*lhs* nesnesinin adresi *rhs* nesnesinin adresinden daha azsa TRUE döndürür, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işleç `CSid` nesnenin veya `SID` yapının adresine göre hareket eder ve C++ Standart Kitaplık toplama sınıfları ile uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_gt"></a>operatör >

İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ `CSid` taraftaki nesne veya `SID` yapıdan büyük olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak `CSid` ilk `SID` nesne veya yapı.

*Rhs*<br/>
Karşılaştırılacak `CSid` ikinci `SID` nesne veya yapı.

### <a name="return-value"></a>Dönüş Değeri

*Lhs* adresi *rhs*adresinden büyükse DOĞRU döndürür , aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işleç `CSid` nesnenin veya `SID` yapının adresine göre hareket eder ve C++ Standart Kitaplık toplama sınıfları ile uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_lt__eq"></a>operatör <=

İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ taraftaki `CSid` nesne `SID` veya yapıdan daha az veya eşit olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak `CSid` ilk `SID` nesne veya yapı.

*Rhs*<br/>
Karşılaştırılacak `CSid` ikinci `SID` nesne veya yapı.

### <a name="return-value"></a>Dönüş Değeri

*Lhs* adresi *rhs*adresidaha az veya eşit ise DOĞRU döndürür , FALSE aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işleç `CSid` nesnenin veya `SID` yapının adresine göre hareket eder ve C++ Standart Kitaplık toplama sınıfları ile uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_gt__eq"></a>operatör >=

İşleticinin `CSid` `SID` sol tarafındaki nesne veya yapının sağ taraftaki `CSid` nesne `SID` veya yapıdan büyük veya eşit olup olmadığını sınar (C++ Standart Kitaplık uyumluluğu için).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
Karşılaştırılacak `CSid` ilk `SID` nesne veya yapı.

*Rhs*<br/>
Karşılaştırılacak `CSid` ikinci `SID` nesne veya yapı.

### <a name="return-value"></a>Dönüş Değeri

*Lhs* adresi *rhs*adresinden daha büyük veya eşit ise DOĞRU döndürür , FALSE aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işleç `CSid` nesnenin veya `SID` yapının adresine göre hareket eder ve C++ Standart Kitaplık toplama sınıfları ile uyumluluk sağlamak için uygulanır.
