---
title: Özel derleme adımı özellikleri (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/17/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 0ec787826a09379732ac00fa858d32f05cf8025b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326078"
---
# <a name="custom-build-step-properties-linux-c"></a>Özel derleme adımı özellikleri (Linux C++)

Özellik | Açıklama
--- | ---
Komut satırı | Özel derleme adımı tarafından yürütülecek komut.
Açıklama | Özel derleme adımı çalıştırıldığında görüntülenen ileti.
Çıktılar | Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir.
{1&gt;Ek Bağımlılıklar&lt;1} | Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi.
Sonra yürütün ve önce yürütme | Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir.
Çıkışı İçerik Olarak Değerlendir | Bu seçenek, yalnızca tüm içerik dosyalarının .appx paketinde pdb'lerini Microsoft Store veya Windows Phone uygulamaları için anlamlıdır.