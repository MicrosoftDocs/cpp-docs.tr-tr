---
title: _variant_t ayıklayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
dev_langs:
- C++
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a9d4e13a4b7382d15e601eba16a5a12edd2d00f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034154"
---
# <a name="variantt-extractors"></a>_variant_t Ayıklayıcıları

**Microsoft'a özgü**

Kapsüllenmiş verileri ayıklamak `VARIANT` nesne.

## <a name="syntax"></a>Sözdizimi

```
operator short( ) const; 
operator long( ) const; 
operator float( ) const; 
operator double( ) const; 
operator CY( ) const; 
operator _bstr_t( ) const; 
operator IDispatch*( ) const; 
operator bool( ) const; 
operator IUnknown*( ) const; 
operator DECIMAL( ) const; 
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>Açıklamalar

Bir kapsüllenmiş ham verileri ayıklar `VARIANT`. Varsa `VARIANT` zaten uygun türde değil `VariantChangeType` bir dönüştürme denemek için kullanılır ve başarısızlık durumunda bir hata oluşturulur:

- **kısa () işleci** ayıklar bir **kısa** tamsayı değeri.

- **uzun () işleci** ayıklar bir **uzun** tamsayı değeri.

- **float () işleci** ayıklar bir **float** sayısal değer.

- **çift () işleci** ayıklar bir **çift** tamsayı değeri.

- **CY () işleci** ayıklar bir `CY` nesne.

- **işleç bool (')** ayıklar bir **bool** değeri.

- **ONDALIK () işleci** ayıklar bir `DECIMAL` değeri.

- **işleç (bayt)** ayıklar bir `BYTE` değeri.

- **işleç _bstr_t (')** bir dize içinde kapsüllenir ayıklar bir `_bstr_t` nesne.

- **IDispatch işleci\*()** dispinterface işaretçi kapsüllenmiş ayıklar `VARIANT`. `AddRef` Çağrı size, bu nedenle, elde edilen işaretçi üzerinde çağrılır `Release` ücretsiz için.

- **IUnknown işleci\*()** bir kapsüllenmiş COM arabirimi işaretçisini ayıklar `VARIANT`. `AddRef` Çağrı size, bu nedenle, elde edilen işaretçi üzerinde çağrılır `Release` ücretsiz için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)