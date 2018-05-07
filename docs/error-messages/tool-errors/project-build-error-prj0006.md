---
title: Proje derleme hatası PRJ0006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0006
dev_langs:
- C++
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 151c22bf13c13de21e89a5c96185cf1c4c1ca349
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0006"></a>Proje Derleme Hatası PRJ0006
Geçici dosya 'dosyası açılamadı. Dosyanın varolduğunu ve dizin değil yazma korumalı emin olun.  
  
 Visual C++ derleme sırasında geçici dosya oluşturulamadı. Buna ilişkin nedenler:  
  
-   Geçici dizin yok.  
  
-   Salt okunur temp dizini.  
  
-   Disk alanı yok.  
  
-   $(Intdir) ya da klasördür salt okunur veya salt okunur geçici dosyaları içerir.  
  
 Bu hata ayrıca hatası PRJ0007 ortaya çıkar: Çıktı 'dizin' oluşturulamadı. Hatası PRJ0007 $(ıntdir) dizin oluşturulamadı, geçici dosyaları oluşturma olduğunu belirtmek de başarısız olacak anlamına gelir.  
  
 Belirttiğiniz her geçici dosyalar oluşturulur:  
  
-   Bir yanıt dosyası.  
  
-   Özel derleme adımı.  
  
-   Bir yapı olayı.