---
title: _com_error::HRESULTToWCode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0ddac28c4f39cdf11abbdf38c3af5d00c22413a
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401912"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft'a özgü**  
  
 16 bit için 32 bitlik HRESULT eşler `wCode`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 *İK*  
 16 bit eşlenmesi 32 bitlik HRESULT `wCode`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 16-bit `wCode` 32 bitlik HRESULT eşlenmiş.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [_com_error::WCode](../cpp/com-error-wcode.md) daha fazla bilgi için.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error Sınıfı](../cpp/com-error-class.md)