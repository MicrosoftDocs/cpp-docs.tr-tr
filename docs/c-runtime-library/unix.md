---
title: UNIX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unix
dev_langs:
- C++
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f5155791f4bf12f15fa0c2c53d27fbe515e5af3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="unix"></a>UNIX
Programlarınıza UNIX bağlantı noktası planlıyorsanız, aşağıdaki yönergeleri izleyin:  
  
-   Üstbilgi dosyaları SYS alt dizinden kaldırmayın. Yalnızca UNIX programlarınıza taşımayı düşünmüyorsanız SYS üstbilgi dosyaları başka bir yere yerleştirebilirsiniz.  
  
-   UNIX uyumlu yol ayırıcısı yol ve bağımsız değişkenler olarak dosya adlarını temsil eden dizeleri ele yordamları kullanın. UNIX Win32 işletim sistemleri her iki ters eğik çizgi destekler ancak bu yalnızca eğik çizgi (/) bu amaçla destekler (\\) ve eğik çizgi (/). Bu nedenle bu belge yolu ayırıcısı olarak UNIX uyumlu eğik kullanan `#include` örneğin deyimleri. (Ancak, Windows işletim sistemi komut kabuğunda cmd EXE desteklemiyor eğik komut isteminde girilen komutlarda.)  
  
-   Yollar ve büyük küçük harfe duyarlı olduğu UNIX içinde düzgün çalışması dosya adları kullanın. Win32 işletim sistemlerinde dosya ayırma tablosu (FAT) dosya sistemi büyük küçük harfe duyarlı değildir; NTFS dosya sistemi durumu dizin listeleri için korur ancak dosya aramaları ve diğer sistem işlemleri durumda yok sayar.  
  
    > [!NOTE]
    >  Visual C++'ın bu sürümünde işlevi açıklamaları UNIX uyumluluk bilgileri kaldırılmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uyumluluk](../c-runtime-library/compatibility.md)