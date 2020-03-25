---
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
ms.openlocfilehash: 685df7285e58e0cf2ceeded5ac27641364897298
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187706"
---
# <a name="_variant_t-extractors"></a>_variant_t Ayıklayıcıları

**Microsoft 'a özgü**

Encapsulated `VARIANT` nesnesinden veri ayıklayın.

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

Encapsulated `VARIANT`ham verileri ayıklar. `VARIANT` zaten uygun türde değilse, `VariantChangeType` dönüştürmeyi denemek için kullanılır ve hata sonrasında bir hata oluşturulur:

- **işleç Short ()** **Kısa** tamsayı değerini ayıklar.

- **Long işleci ()** **Uzun** bir tamsayı değeri ayıklar.

- **float () işleci** **Kayan** sayısal değer ayıklar.

- **Double işleci ()** **Çift** tamsayı değerini ayıklar.

- **() işleci** `CY` nesnesini ayıklar.

- **operator bool ()** Bir **bool** değeri ayıklar.

- **IŞLEÇ ondalık ()** `DECIMAL` değerini ayıklar.

- **IŞLEÇ baytı ()** `BYTE` değerini ayıklar.

- **işleç _bstr_t ()** `_bstr_t` nesnesinde kapsüllenmiş bir dize ayıklar.

- **operatör ıdispatch\*()** Kapsüllenmiş bir `VARIANT`bir dispınterface işaretçisi ayıklar. `AddRef`, sonuç İşaretçisinde çağrılır, bu nedenle onu serbest bırakmak için `Release` çağırmak sizin için kullanılır.

- **Işleç ıunknown\*()** Kapsüllenmiş bir `VARIANT`COM arabirim işaretçisini ayıklar. `AddRef`, sonuç İşaretçisinde çağrılır, bu nedenle onu serbest bırakmak için `Release` çağırmak sizin için kullanılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
