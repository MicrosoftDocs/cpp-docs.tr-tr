---
title: "Önemli hata C1902 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e5f6c22ea848a49a12cc85508fd80a4cfcb90e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1902"></a>Önemli hata C1902
Program veritabanı yöneticisi uyuşmazlığı; Lütfen yüklemenizi denetleyin  
  
Program veritabanı dosyası (.pdb) mspdb daha yeni bir sürümü kullanılarak oluşturulmuş*XXX*derleyici sisteminizde bulunan olandan .dll. Bu hata genellikle mspdbsrv.exe veya mspdbcore.dll eksik veya mspdb daha farklı sürümlerde gösterir*XXX*.dll. ( *XXX* mspdb yer tutucu*XXX*.dll dosya adı değişiklikleri her ürün sürümüne sahip. Örneğin, Visual Studio 2015 ' te dosya mspdb140.dll adıdır.)  
  
Mspdbsrv.exe, mspdbcore.dll ve mspdb eşleşen sürümleri olun*XXX*.dll sisteminizde yüklü. Eşleşmeyen sürümleri hedef platformunuz için derleyici ve bağlantı araçlarını içeren dizine kopyalanmadı emin olun. Derleyici veya bağlantı aracı ayarı olmadan komut isteminden çağıramadı şekilde Örneğin, dosyaları kopyaladığınız **yolu** ortam değişkeni buna göre.