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
ms.workload: cplusplus
ms.openlocfilehash: 0ee183c24cf330b54a335efbd0bbe2b00e18d209
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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