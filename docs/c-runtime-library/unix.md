---
title: UNIX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2403eb0fbe19f83df3909c9d8b765f00fed82c8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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