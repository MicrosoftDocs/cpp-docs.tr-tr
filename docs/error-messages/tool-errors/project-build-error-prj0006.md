---
title: "Proje derleme hatası PRJ0006 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0006
dev_langs: C++
helpviewer_keywords: PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 817450fb6b72f985d7ff49f7e65f9dfa0933b4d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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