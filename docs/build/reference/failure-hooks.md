---
title: Hata kancaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be598a77ca48eeee03360a3b598b0567abc6ee4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="failure-hooks"></a>Hata Kancaları
Aynı şekilde hatası kanca etkin [bildirim kanca](../../build/reference/notification-hooks.md). Böylece işleme uygun değeri döndürmek için kanca rutin gereksinimlerini (bir HINSTANCE veya FARPROC) devam edebilir veya bir özel durum olduğunu göstermek için 0.  
  
 Kullanıcı tanımlı işlev için başvuruyor işaretçi değişkeninin şöyledir:  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 **DelayLoadInfo** yapısı doğru değeri de dahil olmak üzere, hata raporlama için gerekli tüm ilgili verileri içeren `GetLastError`.  
  
 Bildirim ise **dliFailLoadLib**, kanca işlevini döndürebilirsiniz:  
  
-   0, hata yürütemiyorsa.  
  
-   Hata kanca sorunun giderilmiş ve kitaplık yüklenen bir hModule'ü.  
  
 Bildirim ise **dliFailGetProc**, kanca işlevini döndürebilirsiniz:  
  
-   0, hata yürütemiyorsa.  
  
-   Geçerli proc adresine (içeri aktarma işlevi adresi), hata kanca varsa başarılı adresi alma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata İşleme ve Bildirme](../../build/reference/error-handling-and-notification.md)