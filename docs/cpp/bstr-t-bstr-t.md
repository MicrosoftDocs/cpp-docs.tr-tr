---
title: _bstr_t::_bstr_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::_bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0dc49e5fa6b8899e4c9ca6bb15feeebb9cc0fe3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtbstrt"></a>_bstr_t::_bstr_t
**Microsoft özel**  
  
 Oluşturan bir `_bstr_t` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_bstr_t( ) throw( );   
_bstr_t(  
   const _bstr_t& s1   
) throw( );  
_bstr_t(  
   const char* s2   
);  
_bstr_t(  
   const wchar_t* s3   
);  
_bstr_t(  
   const _variant_t& var   
);  
_bstr_t(  
   BSTR bstr,  
   bool fCopy   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `s1`  
 A `_bstr_t` kopyalanacak nesne.  
  
 `s2`  
 Birden çok baytlı bir dize.  
  
 `s3`  
 Bir UNICODE dizesi  
  
 `var`  
 A [_variant_t](../cpp/variant-t-class.md) nesnesi.  
  
 `bstr`  
 Varolan bir `BSTR` nesnesi.  
  
 `fCopy`  
 Varsa `false`, `bstr` bağımsız değişkeni bağlı yeni nesneye çağırarak bir kopyasını yapmadan `SysAllocString`.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda açıklanmaktadır `_bstr_t` oluşturucular.  
  
|Oluşturucu|Açıklama|  
|-----------------|-----------------|  
|`_bstr_t( )`|Varsayılan yapıları `_bstr_t` null yalıtan nesne `BSTR` nesne.|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|Oluşturan bir `_bstr_t` nesnesi başka bir kopyasını olarak.<br /><br /> Bu bir *yüzeysel* kapsüllenmiş başvurusu sayısını artırır kopyalama `BSTR` yeni bir tane oluşturmak yerine nesne.|  
|`_bstr_t( char*`  `s2`  `)`|Oluşturan bir `_bstr_t` çağırarak nesne `SysAllocString` yeni `BSTR` nesnesi ve ardından kapsüller.<br /><br /> Bu oluşturucu, ilk çok baytlı Unicode dönüştürme gerçekleştirir.|  
|`_bstr_t( wchar_t*`  `s3`  `)`|Oluşturan bir `_bstr_t` çağırarak nesne `SysAllocString` yeni `BSTR` nesnesi ve ardından kapsüller.|  
|`_bstr_t( _variant_t&`  `var`  `)`|Yapıları bir `_bstr_t` nesnesinin bir `_variant_t` ilk alarak nesnesi bir `BSTR` kapsüllenmiş değişken nesnesinden nesnesi.|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Oluşturan bir `_bstr_t` varolan bir nesne `BSTR` (tersine bir `wchar_t*` dize). Varsa `fCopy` false, sağlanan `BSTR` ile yeni bir kopya yapmadan yeni nesneye bağlı `SysAllocString`.<br /><br /> Bu Oluşturucu Tür kitaplığı üstbilgi sarmalayıcı işlevleri kapsüllemek ve sahipliğini almak için kullandığı bir `BSTR` bir arabirim yöntemi tarafından döndürülen.|  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t sınıfı](../cpp/bstr-t-class.md)   
 [_variant_t Sınıfı](../cpp/variant-t-class.md)