---
title: "Komut satırı hatası D8027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D8027
dev_langs: C++
helpviewer_keywords: D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bd66688dbf582bf38fb9a0a3706663db3cf145d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-error-d8027"></a>Komut Satırı Hatası D8027
'bileşeni' yürütülemiyor  
  
 Derleyici verilen derleyici bileşeni veya bağlayıcı çalıştıramadı.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Bileşeni yüklemek için yeterli bellek yok. NMAKE derleyici başlatılırsa, derleme görevleri dosyası dışında derleyici çalıştırın.  
  
2.  Geçerli işletim sistemi bileşeni çalıştıramadı. Yol noktalarını yürütülebilir dosyalar işletim sisteminize sağlayın.  
  
3.  Bileşen bozulmuş. Kurulum programını kullanarak dağıtım disklerden bileşeni yeniden kopyalanması.  
  
4.  Bir seçenek hatalı şekilde belirtildi. Örneğin:  
  
    ```  
    cl /B1 file1.c  
    ```