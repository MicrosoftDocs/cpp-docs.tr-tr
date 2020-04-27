---
title: ATL İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: fe5363d3d05123c17e45254898e2210797400022
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168858"
---
# <a name="atl-operators"></a>ATL İşleçleri

Bu bölüm, ATL genel işleçleri için başvuru konularını içerir.

|İşleç|Açıklama|
|--------------|-----------------|
|[işleç = =](#operator_eq_eq)|, Eşitlik `CSid` için iki `SID` nesne veya yapıyı karşılaştırır.|
|[işleç! =](#operator_neq)|Eşitsizlik için `CSid` iki nesne `SID` veya yapıyı karşılaştırır.|
|[işleç <](#operator_lt)|İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıdan daha küçük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).|
|[işleç >](#operator_gt)|İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıdan daha büyük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).|
|[işleç <=](#operator_lt__eq)|İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıya eşit veya ondan küçük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).|
|[işleç >=](#operator_gt__eq)|İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıya eşit veya ondan büyük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h.

## <a name="operator-"></a><a name="operator_eq_eq"></a>işleç = =

Eşitlik `CSid` için nesneleri `SID` veya (güvenlik tanımlayıcısı) yapılarını karşılaştırır.

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

## <a name="operator-"></a><a name="operator_neq"></a>işleç! =

Eşitsizlik `CSid` için nesneleri `SID` veya (güvenlik tanımlayıcısı) yapılarını karşılaştırır.

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

## <a name="operator-"></a><a name="operator_lt"></a>işleç <

İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıdan daha küçük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).

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

Bu işleç, `CSid` nesne veya `SID` yapının adresi üzerinde davranır ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_gt"></a>işleç >

İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıdan daha büyük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

*LHS* adresinin *RHS*adresınden büyük olması durumunda true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSid` nesne veya `SID` yapının adresi üzerinde davranır ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_lt__eq"></a>işleç <=

İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıya eşit veya ondan küçük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

*LHS* adresinin *RHS*adresinden küçük veya ona eşit olması durumunda true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSid` nesne veya `SID` yapının adresi üzerinde davranır ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.

## <a name="operator-"></a><a name="operator_gt__eq"></a>işleç >=

İşlecin sol tarafındaki `CSid` nesnenin veya `SID` yapının sağ taraftaki `CSid` nesne veya `SID` yapıya eşit veya ondan büyük olup olmadığını sınar (C++ standart kitaplık uyumluluğu için).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk `CSid` nesne veya `SID` yapı.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci `CSid` nesne veya `SID` yapı.

### <a name="return-value"></a>Dönüş Değeri

*LHS* adresinin *RHS*adresinden büyük veya ona eşit olması durumunda true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSid` nesne veya `SID` yapının adresi üzerinde davranır ve C++ standart kitaplık koleksiyonu sınıflarıyla uyumluluk sağlamak için uygulanır.
