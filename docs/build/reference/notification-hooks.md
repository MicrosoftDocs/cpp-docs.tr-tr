---
title: Bildirim kancaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0210c4ee058694594893a029789442c89003da2e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377825"
---
# <a name="notification-hooks"></a>Bildirim Kancaları
Yalnızca aşağıdaki eylemleri içindeki Yardımcısı yordamı gerçekleştirmeden önce bildirim kancaları çağrılır:  
  
-   Kitaplıkta depolanan tanıtıcısı, önceden yüklenip yüklenmediğini görmek için denetlenir.  
  
-   **LoadLibrary** DLL yükünü denemeye olarak adlandırılır.  
  
-   **GetProcAddress** yordam adresini alma girişimi için çağrılır.  
  
-   Gecikme alma yük dönüştürücü döndür.  
  
 Bildirim kanca etkinleştirilir:  
  
-   İşaretçinin yeni bir tanımı sağlayarak **__pfnDliNotifyHook2** bildirimleri alan kendi işlevi işaret edecek şekilde başlatıldı.  
  
     -veya-  
  
-   İşaretçinin ayarlayarak **__pfnDliNotifyHook2** yükleme programı DLL yapılan her çağrı gecikme önce kanca işlevi.  
  
 Bildirim ise **dliStartProcessing**, kanca işlevini döndürebilirsiniz:  
  
 NULL  
 Varsayılan yardımcı DLL yüklenmesini işler. Bu yalnızca bilgilendirme amaçlıdır çağrılacak yararlıdır.  
  
 işlev işaretçisi  
 Varsayılan gecikme yükü işleme atlama. Bu, kendi yük işleyici sağlamanıza olanak tanır.  
  
 Bildirim ise **dliNotePreLoadLibrary**, kanca işlevini döndürebilirsiniz:  
  
-   0, yalnızca bilgilendirme bildirimleri isterse.  
  
-   HModule'ü DLL yüklerse yüklenen DLL için.  
  
 Bildirim ise **dliNotePreGetProcAddress**, kanca işlevini döndürebilirsiniz:  
  
-   0, yalnızca bilgilendirme bildirimleri isterse.  
  
-   Kanca işlevini adresi alırsa içeri aktarılan işlevin adresi.  
  
 Bildirim ise **dliNoteEndProcessing**, kanca işlevin dönüş değeri yoksayılır.  
  
 This işaretçisi (sıfır) başlatılırsa, Gecikmeli Yükleme Yardımcısı yürütülmesinin boyunca belirli bildirim noktalarda işlevi çağırır. İşlev işaretçisi aşağıdaki tanımı vardır:  
  
```  
// The "notify hook" gets called for every call to the  
// delay load helper.  This allows a user to hook every call and  
// skip the delay load helper entirely.  
//  
// dliNotify == {  
//  dliStartProcessing |  
//  dliNotePreLoadLibrary  |  
//  dliNotePreGetProc |  
//  dliNoteEndProcessing}  
//  on this call.  
//  
ExternC  
PfnDliHook   __pfnDliNotifyHook2;  
  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 Bildirimleri geçirin bir **DelayLoadInfo** bildirim değeri birlikte kanca işlevini yapısına. Bu veriler Gecikmeli Yükleme Yardımcısı yordamı tarafından kullanılan aynıdır. Bildirim değer tanımlanan değerlerden biri olacaktır [yapı ve sabit tanımları](../../build/reference/structure-and-constant-definitions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata İşleme ve Bildirme](../../build/reference/error-handling-and-notification.md)