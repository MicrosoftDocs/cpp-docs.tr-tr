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
ms.openlocfilehash: e5a443b5f80eabe9691cf8ff5220bb9b66da51e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052575"
---
# <a name="fatal-error-c1902"></a>Önemli hata C1902

Program veritabanı yöneticisi uyuşmazlığı; Lütfen yüklemenizi denetleyin

Program veritabanı dosyası (.pdb) mspdb daha yeni bir sürümü kullanılarak oluşturulmuş olan*XXX*derleyici sisteminizde bulunan bir .dll. Bu hata genellikle mspdbsrv.exe veya mspdbcore.dll eksik veya mspdb farklı sürümlerine sahip gösterir*XXX*.dll. ( *XXX* mspdb yer tutucu*XXX*her ürün sürümüyle .dll dosya adı değişiyor. Örneğin, Visual Studio 2015'te dosya mspdb140.dll adıdır.)

Eşleşen sürümlerini mspdbsrv.exe mspdbcore.dll ve mspdb olun*XXX*.dll, sisteminize yüklenir. Eşleşmeyen sürümler hedef platform için derleyici ve bağlantı araçlarını içeren dizine kopyalanmadı emin olun. Derleyici veya bağlantı aracı komut isteminde ayarlamadan çağırabilirsiniz böylece Örneğin, dosyalar kopyaladığınız **yolu** ortam değişkeni buna göre.