---
title: _bstr_t::wchar_t *, _bstr_t::char * | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs: C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c078b727c42bb4704cfc3867cc22592f49a63e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t*, _bstr_t::char*
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
 [_bstr_t sınıfı](../cpp/bstr-t-class.md)