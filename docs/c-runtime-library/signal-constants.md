---
title: Sinyal sabitleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e47e3e7bce5a41e055f251d906ec72d98c5b285
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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