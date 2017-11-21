---
title: _com_error::WCodeToHRESULT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::WCodeToHRESULT
dev_langs: C++
helpviewer_keywords: WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 925e1f7a2675dc0aaed3a0cab064e01681de673c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft özel**  
  
 16 bit `wCode`'u 32 bit `HRESULT` ile eşleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `wCode`  
 32 bit `wCode` ile eşleştirilecek 16 bit `HRESULT`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 16 bit `HRESULT`'dan eşleştirilmiş 32 bit `wCode`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [WCode](../cpp/com-error-wcode.md) üye işlevi.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error sınıfı](../cpp/com-error-class.md)