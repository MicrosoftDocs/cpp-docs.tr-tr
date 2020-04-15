---
title: Özel Yapı Adım Özellikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
ms.openlocfilehash: 67b281e245c4fff8f37baff8875cbc3dc84ca718
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79441335"
---
# <a name="custom-build-step-properties-linux-c"></a>Özel Yapı Adım Özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Özel derleme adımı tarafından yürütülecek komut. |
| Açıklama | Özel derleme adımı çalıştırıldığında görüntülenen ileti. |
| Çıkışlar | Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir. |
| Ek Bağımlılıklar | Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi. |
| Daha Önce Çalıştır Ve Çalıştır | Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir. |
| Çıkışı İçerik Olarak Değerlendir | Bu seçenek, .appx paketindeki tüm içerik dosyalarını içeren Microsoft Mağazası veya Windows Phone uygulamaları için yalnızca anlamlıdır. |

::: moniker-end
