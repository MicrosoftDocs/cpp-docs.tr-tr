---
title: Sinyal sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
dev_langs:
- C++
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 279f4beb3b550f672ac3950c31f3653ca1f00ba2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="signal-constants"></a>sinyal Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `sig` Bağımsız değişkeni (tanımlıysa sinyali. listelenen bildirim sabitler biri olması gerekir H).  
  
 `SIGABRT`  
 Olağan dışı sonlandırma. Varsayılan eylem çağıran program 3 çıkış koduyla sona erer.  
  
 `SIGABRT_COMPAT`  
 SIGABRT ile aynıdır. Diğer platformlar ile uyumluluk için.  
  
 `SIGFPE`  
 Taşma, sıfır veya geçersiz işlem bölme gibi kayan nokta hata oluştu. Varsayılan eylem çağıran program sonlandırır.  
  
 `SIGILL`  
 Geçersiz yönerge. Varsayılan eylem çağıran program sonlandırır.  
  
 `SIGINT`  
 CTRL + C kesme. Varsayılan eylem çağıran program 3 çıkış koduyla sona erer.  
  
 `SIGSEGV`  
 Geçersiz depolama erişim. Varsayılan eylem çağıran program sonlandırır.  
  
 `SIGTERM`  
 Sonlandırma isteği programa gönderilir. Varsayılan eylem çağıran program 3 çıkış koduyla sona erer.  
  
 `SIG_ERR`  
 Hata belirten bir sinyal dönüş türünden oluştu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sinyal](../c-runtime-library/reference/signal.md)   
 [Yükselt](../c-runtime-library/reference/raise.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)