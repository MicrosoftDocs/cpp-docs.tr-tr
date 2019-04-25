---
title: Önemli hata C1902
ms.date: 11/04/2016
f1_keywords:
- C1902
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
ms.openlocfilehash: c425430a6d08ae8a97c4dcd0f5764f44dee43e5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165872"
---
# <a name="fatal-error-c1902"></a>Önemli hata C1902

Program veritabanı yöneticisi uyuşmazlığı; Lütfen yüklemenizi denetleyin

Program veritabanı dosyası (.pdb) mspdb daha yeni bir sürümü kullanılarak oluşturulmuş olan*XXX*derleyici sisteminizde bulunan bir .dll. Bu hata genellikle mspdbsrv.exe veya mspdbcore.dll eksik veya mspdb farklı sürümlerine sahip gösterir*XXX*.dll. ( *XXX* mspdb yer tutucu*XXX*her ürün sürümüyle .dll dosya adı değişiyor. Örneğin, Visual Studio 2015'te dosya mspdb140.dll adıdır.)

Eşleşen sürümlerini mspdbsrv.exe mspdbcore.dll ve mspdb olun*XXX*.dll, sisteminize yüklenir. Eşleşmeyen sürümler hedef platform için derleyici ve bağlantı araçlarını içeren dizine kopyalanmadı emin olun. Derleyici veya bağlantı aracı komut isteminde ayarlamadan çağırabilirsiniz böylece Örneğin, dosyalar kopyaladığınız **yolu** ortam değişkeni buna göre.