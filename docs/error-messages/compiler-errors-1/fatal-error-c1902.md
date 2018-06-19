---
title: Önemli hata C1902 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b23507b6531f9ee4e5ce5efd5b60a1977206635c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228205"
---
# <a name="fatal-error-c1902"></a>Önemli hata C1902
Program veritabanı yöneticisi uyuşmazlığı; Lütfen yüklemenizi denetleyin  
  
Program veritabanı dosyası (.pdb) mspdb daha yeni bir sürümü kullanılarak oluşturulmuş*XXX*derleyici sisteminizde bulunan olandan .dll. Bu hata genellikle mspdbsrv.exe veya mspdbcore.dll eksik veya mspdb daha farklı sürümlerde gösterir*XXX*.dll. ( *XXX* mspdb yer tutucu*XXX*.dll dosya adı değişiklikleri her ürün sürümüne sahip. Örneğin, Visual Studio 2015 ' te dosya mspdb140.dll adıdır.)  
  
Mspdbsrv.exe, mspdbcore.dll ve mspdb eşleşen sürümleri olun*XXX*.dll sisteminizde yüklü. Eşleşmeyen sürümleri hedef platformunuz için derleyici ve bağlantı araçlarını içeren dizine kopyalanmadı emin olun. Derleyici veya bağlantı aracı ayarı olmadan komut isteminden çağıramadı şekilde Örneğin, dosyaları kopyaladığınız **yolu** ortam değişkeni buna göre.