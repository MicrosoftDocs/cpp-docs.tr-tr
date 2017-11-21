---
title: Dosya izin sabitleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs: C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aa42ebf645c737ffe2f5db9647a3ba3912669b27
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="file-permission-constants"></a>Dosya İzin Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabitleri biri gereklidir `_O_CREAT` (`_open`, `_sopen`) belirtilir.  
  
 `pmode` Bağımsız değişkeni aşağıdaki gibi dosyanın izin ayarlarını belirtir.  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_S_IREAD`|Okuma izin verilir|  
|`_S_IWRITE`|İzin verilen yazma|  
|`_S_IREAD` &#124; `_S_IWRITE`|Okuma ve yazma izin verilir|  
  
 Olarak kullanıldığında `pmode` bağımsız değişkeni için `_umask`, Bildirim sabiti izni ayarı gibi ayarlar.  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_S_IREAD`|İzin yazma (dosya salt okunur)|  
|`_S_IWRITE`|İzin okuma (dosya salt yazılır)|  
|`_S_IREAD` &#124; `_S_IWRITE`|Ne okuma ne de izin yazma|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_kurulum Aç, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../c-runtime-library/reference/umask.md)   
 [Standart Türler](../c-runtime-library/standard-types.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)