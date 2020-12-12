---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t:: operator + =, +'
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: e3ae71a3a43e189251ac0ddaf77572656a031aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308815"
---
# <a name="_bstr_toperator--"></a>_bstr_t::operator +=, +

**Microsoft'a Özgü**

Nesnenin sonuna karakter ekler `_bstr_t` veya iki dizeyi birleştirir.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>Parametreler

*S1*<br/>
Bir `_bstr_t` nesnesi.

*S2*<br/>
Çok baytlı bir dize.

*bekletmeden*<br/>
Unicode dizesi.

## <a name="remarks"></a>Açıklamalar

Bu işleçler dize birleştirmesi gerçekleştirir:

- **işleç + = (***S1***)** S1 'in kapsüllenmiş içindeki karakterleri `BSTR` Bu nesnenin  kapsüllendiği uca ekler `BSTR` .    

- **operator + (***S1***)** `_bstr_t`Bu nesnenin S1 ile birleştirerek oluşturulan yeni bir döndürür `BSTR` .     

- **operator + (***S2* **&#124;** *S1***)** `_bstr_t`S1 içinde kapsülle birlikte, bir çok baytlı dize olan *S2*'yi birleştirerek oluşturulan yeni bir döndürür `BSTR` .         

- **operator + (***S3* **,***S1***)** `_bstr_t`S1 içinde kapsüllenmiş ile bir Unicode dize *S3* ile birleştirerek oluşturulan yeni bir döndürür `BSTR` .       

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
