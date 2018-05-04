---
title: _bstr_t::wchar_t *, _bstr_t::char* | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs:
- C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55225ba97848b2b503742d15ccf032e99342f0be
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t *, _bstr_t::char*
**Microsoft özel**  
  
 BSTR karakterleri dar veya uluslararası karakter dizisi olarak döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleçlere yalıtılan karakter verileri ayıklamak için kullanılabilir `BSTR` nesnesi. Yeni bir değer döndürülen işaretçi atayarak özgün BSTR verileri değiştirmez.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)