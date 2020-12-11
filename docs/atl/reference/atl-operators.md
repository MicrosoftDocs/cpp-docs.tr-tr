---
description: 'Daha fazla bilgi edinin: ATL Işleçleri'
title: ATL İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 8c336732aeee9146b89e300580c0fbee506ec343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158692"
---
# <a name="atl-operators"></a>ATL İşleçleri

Bu bölüm, ATL genel işleçleri için başvuru konularını içerir.

|İşleç|Açıklama|
|--------------|-----------------|
|[işleç = =](#operator_eq_eq)|, `CSid` Eşitlik için iki nesne veya `SID` yapıyı karşılaştırır.|
|[işleç! =](#operator_neq)|`CSid`Eşitsizlik için iki nesne veya `SID` yapıyı karşılaştırır.|
|[işleç <](#operator_lt)|`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının `CSid` sağ taraftaki nesne veya yapıdan daha küçük olup olmadığını sınar `SID` (C++ standart kitaplık uyumluluğu için).|
|[işleç >](#operator_gt)|`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının `CSid` sağ taraftaki nesne veya yapıdan daha büyük olup olmadığını sınar `SID` (C++ standart kitaplık uyumluluğu için).|
|[işleç <=](#operator_lt__eq)|`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının sağ taraftaki nesne veya yapıya eşit veya ondan küçük olup olmadığını sınar `CSid` `SID` (C++ standart kitaplık uyumluluğu için).|
|[işleç >=](#operator_gt__eq)|`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının sağ taraftaki nesne veya yapıya eşit veya ondan büyük olup olmadığını sınar `CSid` `SID` (C++ standart kitaplık uyumluluğu için).|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h.

## <a name="operator-"></a><a name="operator_eq_eq"></a> işleç = =

`CSid` `SID` Eşitlik için nesneleri veya (güvenlik tanımlayıcısı) yapılarını karşılaştırır.

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse TRUE, eşitse FALSE değerini döndürür.

## <a name="operator-"></a><a name="operator_neq"></a> işleç! =

`CSid` `SID` Eşitsizlik için nesneleri veya (güvenlik tanımlayıcısı) yapılarını karşılaştırır.

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşit değilse TRUE, eşitse FALSE döndürür.

## <a name="operator-"></a><a name="operator_lt"></a> işleç <

`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının `CSid` sağ taraftaki nesne veya yapıdan daha küçük olup olmadığını sınar `SID` (C++ standart kitaplık uyumluluğu için).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

*LHS* nesnesinin adresinin *RHS* nesnesinin adresınden küçük olması durumunda true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSid` nesne veya yapının adresi üzerinde davranır `SID` ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_gt"></a> işleç >

`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının `CSid` sağ taraftaki nesne veya yapıdan daha büyük olup olmadığını sınar `SID` (C++ standart kitaplık uyumluluğu için).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

*LHS* adresinin *RHS* adresınden büyük olması durumunda true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSid` nesne veya yapının adresi üzerinde davranır `SID` ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_lt__eq"></a> işleç <=

`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının sağ taraftaki nesne veya yapıya eşit veya ondan küçük olup olmadığını sınar `CSid` `SID` (C++ standart kitaplık uyumluluğu için).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

*LHS* adresinin *RHS* adresinden küçük veya ona eşit olması durumunda true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSid` nesne veya yapının adresi üzerinde davranır `SID` ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_gt__eq"></a> işleç >=

`CSid` `SID` İşlecin sol tarafındaki nesnenin veya yapının sağ taraftaki nesne veya yapıya eşit veya ondan büyük olup olmadığını sınar `CSid` `SID` (C++ standart kitaplık uyumluluğu için).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

*LHS* adresinin *RHS* adresinden büyük veya ona eşit olması durumunda true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSid` nesne veya yapının adresi üzerinde davranır `SID` ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.
