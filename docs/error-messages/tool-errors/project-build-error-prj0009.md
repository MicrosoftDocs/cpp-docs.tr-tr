---
title: "Proje derleme hatası PRJ0009 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0009
dev_langs: C++
helpviewer_keywords: PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4793a4541c133372e7833853caad174303f2a9dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0009"></a>Proje Derleme Hatası PRJ0009
Yapı günlük yazma için açılamadı.  
  
 **Dosya başka bir işlem tarafından açık değil ve yazma korumalı olmadığından emin olun.**  
  
 Ayar sonra **derleme günlüğü** özelliğine **Evet** ve derleme veya yeniden gerçekleştirmeden, Visual C++ derleme günlüğünde özel modda açamadı.  
  
 İncelemek **derleme günlüğü** açarak ayarı **seçenekleri** iletişim kutusu (üzerinde **Araçları** menüsünde tıklatın **seçenekleri** komutu) ve ardından seçme **VC ++ yapı** içinde **projeleri** klasör. Derleme dosyası BuildLog.htm olarak adlandırılır ve Ara dizin $(IntDir) yazılır.  
  
 Bu hata için olası nedenler:  
  
-   Visual C++ iki işlemleri çalıştırdığınız ve aynı yapılandırması aynı projesinin hem de aynı anda oluşturmak çalışıyor.  
  
-   Yapı günlük dosyası dosyayı kilitler bir işlemde açılır.  
  
-   Kullanıcının bir dosyayı oluşturma izni yok.  
  
-   Geçerli kullanıcının BuildLog.htm dosyasına yazma erişimi yok.