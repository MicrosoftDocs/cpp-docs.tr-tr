---
title: "Önemli hata C1902 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1902
dev_langs: C++
helpviewer_keywords: C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 89354565f67c8704eee8c8b5f9dcb94523800c63
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1902"></a>Önemli hata C1902
Program veritabanı yöneticisi uyuşmazlığı; Lütfen yüklemenizi denetleyin  
  
Program veritabanı dosyası (.pdb) mspdb daha yeni bir sürümü kullanılarak oluşturulmuş*XXX*derleyici sisteminizde bulunan olandan .dll. Bu hata genellikle mspdbsrv.exe veya mspdbcore.dll eksik veya mspdb daha farklı sürümlerde gösterir*XXX*.dll. ( *XXX* mspdb yer tutucu*XXX*.dll dosya adı değişiklikleri her ürün sürümüne sahip. Örneğin, Visual Studio 2015 ' te dosya mspdb140.dll adıdır.)  
  
Mspdbsrv.exe, mspdbcore.dll ve mspdb eşleşen sürümleri olun*XXX*.dll sisteminizde yüklü. Eşleşmeyen sürümleri hedef platformunuz için derleyici ve bağlantı araçlarını içeren dizine kopyalanmadı emin olun. Derleyici veya bağlantı aracı ayarı olmadan komut isteminden çağıramadı şekilde Örneğin, dosyaları kopyaladığınız **yolu** ortam değişkeni buna göre.