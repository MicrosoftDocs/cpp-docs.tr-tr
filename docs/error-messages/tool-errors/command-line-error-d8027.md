---
title: Komut satırı hatası D8027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc93edb939001a1e1bed5d3f7a4113e8483e81dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296126"
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