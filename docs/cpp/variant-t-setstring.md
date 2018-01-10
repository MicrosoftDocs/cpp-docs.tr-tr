---
title: _variant_t::SetString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _variant_t::SetString
dev_langs: C++
helpviewer_keywords: SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c433aafbe9799486d141e04ca747cbb4f7c3e22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Microsoft özel**  
  
 Bir dize için atar `_variant_t` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pSrc`  
 Karakter dizesi işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 ANSI karakter dizesi bir Unicode dönüştürür `BSTR` dize ve bunun için atar `_variant_t` nesnesi.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)