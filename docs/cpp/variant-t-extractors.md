---
description: 'Hakkında daha fazla bilgi edinin: _variant_t ayıklayıcıları'
title: _variant_t Ayıklayıcıları
ms.date: 11/04/2016
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
ms.openlocfilehash: 55a02fdf422388b0e44a9aad77e86f7a76e80e3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161604"
---
# <a name="_variant_t-extractors"></a>_variant_t Ayıklayıcıları

**Microsoft'a Özgü**

Encapsulated nesneden veri ayıklayın `VARIANT` .

## <a name="syntax"></a>Syntax

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

Kapsülden ham verileri ayıklar `VARIANT` . `VARIANT`Zaten uygun tür değilse, `VariantChangeType` dönüştürmeyi denemek için kullanılır ve hata sonrasında bir hata oluşturulur:

- **işleç Short ()** Bir **`short`** tamsayı değeri ayıklar.

- **Long işleci ()** Bir **`long`** tamsayı değeri ayıklar.

- **float () işleci** Sayısal bir **`float`** değer ayıklar.

- **Double işleci ()** Bir **`double`** tamsayı değeri ayıklar.

- **() işleci** Bir `CY` nesneyi ayıklar.

- **operator bool ()** Bir **`bool`** değer ayıklar.

- **IŞLEÇ ondalık ()** Bir `DECIMAL` değer ayıklar.

- **IŞLEÇ baytı ()** Bir `BYTE` değer ayıklar.

- **işleç _bstr_t ()** Bir nesne içinde kapsüllenmiş bir dize ayıklar `_bstr_t` .

- **Işleç IDispatch \* ()** , kapsüllenmiş bir dispınterface işaretçisi ayıklar `VARIANT` . `AddRef` elde edilen işaretçi üzerinde çağrılır `Release` . bu nedenle, serbest bırakmak için çağırmak sizin için kullanılır.

- **IUnknown \* () işleci** , kapsüllenmiş bir com arabirim işaretçisini ayıklar `VARIANT` . `AddRef` elde edilen işaretçi üzerinde çağrılır `Release` . bu nedenle, serbest bırakmak için çağırmak sizin için kullanılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
