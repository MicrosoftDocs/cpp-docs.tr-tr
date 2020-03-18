---
title: Özel derleme adımı özellikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
ms.openlocfilehash: 67b281e245c4fff8f37baff8875cbc3dc84ca718
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441335"
---
# <a name="custom-build-step-properties-linux-c"></a>Özel derleme adımı özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Özel derleme adımı tarafından yürütülecek komut. |
| Açıklama | Özel derleme adımı çalıştırıldığında görüntülenen ileti. |
| Çıkışlar | Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir. |
| {1&gt;Ek Bağımlılıklar&lt;1} | Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi. |
| Önce yürütün ve yürütmeden önce yürütün | Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir. |
| Çıkışı İçerik Olarak Değerlendir | Bu seçenek yalnızca. appx paketindeki tüm içerik dosyalarını içeren Microsoft Store veya Windows Phone uygulamalar için anlamlıdır. |

::: moniker-end
