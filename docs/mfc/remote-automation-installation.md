---
title: "Uzak Otomasyon yüklemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Remote Automation [MFC], installation
- installing Remote Automation [MFC]
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: acd8ee55261dfa03c68aef506dc90188d8d27d37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="remote-automation-installation"></a>Uzak Otomasyon Yüklemesi
Uzak Otomasyon nispeten daha az sayıda bileşeni vardır:  
  
-   Uzak otomasyon istemci proxy, AUTPRX32. DLL.  
  
-   Uzak Otomasyon sunucu tarafı bileşeni, Otomasyon Yöneticisi AUTMGR32. EXE.  
  
-   RAC Yöneticisi RACMGR32 olabilir. EXE eşleşen RACREG32 ile. DLL.  
  
 Bu, RAC Yöneticisi Visual Basic'te yazılır ve bu nedenle Visual Basic çalışma zamanı desteği. Visual C++ Enterprise Edition yüklediğinizde bu ve diğer uzak otomasyon dosyaları Kurulumu tarafından yüklenir.  
  
 Uzak Otomasyon bileşenleri bir bilgisayara kopyalarsanız, hangi Visual C++ sürümü Enterprise Edition yüklü değil, emin olun, REGSRV32. EXE bilgisayarın yoludur ve RACREG32 kaydedin. Aşağıdaki komut satırını kullanarak DLL:  
  
 REGSRVR32 RACREG32. DLL  
  
> [!NOTE]
>  Visual C++ 5.0 önce RAC Manager sürümleri GUAGE32 gereklidir. OCX ve TABCTL32. OCX. Hiçbirini Manager'ın sürümünü RAC birlikte gelen Visual C++ Enterprise Edition, sürüm 5.0 veya üstü ile için gereklidir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Otomasyon Yöneticisi](../mfc/automation-manager-mfc.md)  
  
 [Uzak Otomasyon Bağlantı Yöneticisi](../mfc/remote-automation-connection-manager.md)  
  
 [Uzak Otomasyon Kullanıcı Bileşenleri](../mfc/remote-automation-user-components.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzak Otomasyon](../mfc/remote-automation.md)

