---
title: _com_error::HRESULTToWCode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HRESULTToWCode
dev_langs: C++
helpviewer_keywords: HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dac335f3cc2ea26602a5f8a91a47db7d1ebe39b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft özel**  
  
 32-bit eşlemeleri `HRESULT` için 16 bit `wCode`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hr`  
 32 bit `HRESULT` 16 bit eşlenmesi `wCode`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 16 bit `wCode` 32-bit eşlenen `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [_com_error::WCode](../cpp/com-error-wcode.md) daha fazla bilgi için.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error sınıfı](../cpp/com-error-class.md)