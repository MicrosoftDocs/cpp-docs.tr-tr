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
ms.openlocfilehash: 65049a473f62e728fcb4d74b581a08c0f1723fc9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423324"
---
# <a name="variantt-extractors"></a>_variant_t Ayıklayıcıları
**Microsoft özel**  
  
 Veri kapsüllenmiş ayıklamak **değişken** nesnesi.  
  
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
 Ham veri bir kapsüllenmiş ayıklar **değişken**. Varsa **değişken** zaten uygun türde değil **VariantChangeType** bir dönüştürme denemek için kullanılır ve bir hata hata yapması üzerine oluşturulur:  
  
-   **short işleci ()** ayıklar bir **kısa** tamsayı değeri.  
  
-   **uzun işleci ()** ayıklar bir **uzun** tamsayı değeri.  
  
-   **float işleci ()** ayıklar bir **float** sayısal değer.  
  
-   **double işleci ()** ayıklar bir **çift** tamsayı değeri.  
  
-   **CY () işleci** ayıklar bir **CY** nesnesi.  
  
-   **işleç bool (')** ayıklar bir `bool` değeri.  
  
-   **ONDALIK () işleci** ayıklar bir **ondalık** değeri.  
  
-   **işleci (bayt)** ayıklar bir **bayt** değeri.  
  
-   **işleç _bstr_t (')** içinde kapsüllenir bir dize ayıklar bir `_bstr_t` nesnesi.  
  
-   **IDispatch işleci\*()** görüntüleme arabirimi işaretçisi bir kapsüllenmiş ayıklar **değişken**. `AddRef` Çağrı size olacak şekilde elde edilen işaretçisini adlı **sürüm** onu boşaltılacak.  
  
-   **IUnknown işleci\*()** COM arabirimi işaretçisi bir kapsüllenmiş ayıklar **değişken**. `AddRef` Çağrı size olacak şekilde elde edilen işaretçisini adlı **sürüm** onu boşaltılacak.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)
