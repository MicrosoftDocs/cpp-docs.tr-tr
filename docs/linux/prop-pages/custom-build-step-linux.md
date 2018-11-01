---
title: Özel derleme adımı özellikleri (Linux C++)
ms.date: 10/17/2017
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
ms.openlocfilehash: 5e6580263e63547e3564eaee260158a312e5fa6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644710"
---
# <a name="custom-build-step-properties-linux-c"></a>Özel derleme adımı özellikleri (Linux C++)

Özellik | Açıklama
--- | ---
Komut satırı | Özel derleme adımı tarafından yürütülecek komut.
Açıklama | Özel derleme adımı çalıştırıldığında görüntülenen ileti.
Çıktılar | Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir.
{1&gt;Ek Bağımlılıklar&lt;1} | Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi.
Sonra yürütme ve önce yürütme | Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir.
Çıkışı İçerik Olarak Değerlendir | Bu seçenek, yalnızca tüm içerik dosyalarını .appx paketine dahil, Microsoft Store veya Windows Phone uygulamaları için daha anlamlı olur.