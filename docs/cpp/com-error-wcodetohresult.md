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
ms.workload: cplusplus
ms.openlocfilehash: ca20bfa7574f604187734040b3ccc001d6aaf68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [_com_error Sınıfı](../cpp/com-error-class.md)