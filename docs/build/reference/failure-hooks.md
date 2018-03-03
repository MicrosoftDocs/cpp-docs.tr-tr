---
title: "Hata kancaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1609b713fef253e8beab270ee2ed048466da6504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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