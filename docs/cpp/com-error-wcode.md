---
title: _com_error::WCode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1354d490446795e55b41fa0c548e8dd8aa38c71b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Microsoft özel**  
  
 Kapsüllenmiş eşlenen 16 bit hata kodu alır `HRESULT`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `HRESULT` 0x80040200 için 0x8004FFFF aralığı içinde **WCode** yöntemi döndürür `HRESULT` 0x80040200; Aksi halde, sıfır döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 **WCode** yöntemi COM destek kodda gerçekleşen eşleme geri almak için kullanılır. İçin sarmalayıcı bir **görüntüleme arabirimi** özellik veya yöntem çağrıları ve bağımsız değişkenler paketleri bir destek yordam çağrıları **IDispatch::Invoke**. İade, bir hata varsa üzerine `HRESULT` , `DISP_E_EXCEPTION` döndürülür hata bilgilerini alınır **EXCEPINFO** yapısı geçirilen **IDispatch::Invoke**. Hata kodu olabilir ya da depolanan bir 16 bit değeri `wCode` üyesi **EXCEPINFO** yapısı veya tam 32-bit değerinde **scode** üyesi **EXCEPINFO**yapısı. 16 bit ise `wCode` döndürülür, ilk eşlenmelidir bir 32 bit hata `HRESULT`.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error Sınıfı](../cpp/com-error-class.md)