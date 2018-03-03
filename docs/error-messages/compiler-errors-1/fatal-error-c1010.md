---
title: "Önemli hata C1010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1010
dev_langs:
- C++
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b2123118be2a8a382f6b718499c5af16f88d111
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1010"></a>Önemli hata C1010
Beklenmeyen için önceden derlenmiş üst bilgi arayan sırasında dosya sonu. Eklemeyi mi unuttunuz ' # adını include' kaynağınız için?  
  
 İle belirtilen bir içerme dosyası [/Yu](../../build/reference/yu-use-precompiled-header-file.md) kaynak dosyasında listelenmeyen.  Bu seçenek çoğu Visual C++ proje türleri varsayılan olarak etkindir ve "stdafx.h" varsayılan bu seçeneği tarafından belirtilen dosyasına dahil edilir.  
  
 Visual Studio ortamında, bu hatayı gidermek için aşağıdaki yöntemlerden birini kullanın:  
  
-   Önceden derlenmiş üstbilgiler projenizde kullanmıyorsanız ayarlamak **Oluştur/Kullan önceden derlenmiş üst bilgi** özelliği için kaynak dosyalarının **kullanarak önceden derlenmiş üstbilgi**. Bu derleyici seçeneği belirlemek için aşağıdaki adımları izleyin:  
  
    1.  Çözüm Gezgini bölmesinde projenin proje adına sağ tıklayın ve ardından **özellikleri**.  
  
    2.  Sol bölmede **C/C++** klasör.  
  
    3.  Tıklatın **önceden derlenmiş üstbilgiler** düğümü.  
  
    4.  Sağ bölmede **Oluştur/Kullan önceden derlenmiş üstbilgi**ve ardından **kullanarak önceden derlenmiş üstbilgi**.  
  
-   İstemeden silmiş, yeniden adlandırılmış veya üstbilgi dosyası kaldırılmış olduğundan emin olun (varsayılan olarak, stdafx.h) geçerli projeden. Bu dosya ayrıca başka bir kod kullanarak kaynak dosyalarında önce eklenmesi gerekir **# "stdafx.h" include**. (Bu üstbilgi dosyası olarak belirtilen **aracılığıyla PCH dosya oluştur/kullan** proje özelliği)