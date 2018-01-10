---
title: "Özel derleme adımı özellikleri (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: ae749fa161dba2957f3e621ce42c610153594e66
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="custom-build-step-properties-linux-c"></a>Özel derleme adımı özellikleri (Linux C++)

Özellik | Açıklama
--- | ---
Komut satırı | Özel derleme adımı tarafından yürütülecek komut.
Açıklama | Özel derleme adımı çalıştırıldığında görüntülenen ileti.
Çıktılar | Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir.
Ek Bağımlılıklar | Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi.
Sonra yürütün ve önce yürütme | Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir.
Çıkışı İçerik Olarak Değerlendir | Bu seçenek yalnızca, tüm içerik dosyalarını .appx paketine dahil eden Windows Store veya Windows Phone uygulamaları için anlamlıdır.