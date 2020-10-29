---
title: Özel derleme adımı özellikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
ms.openlocfilehash: 51111b7ff1ab68ecc49b54efdeeef5f95368ab0c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924535"
---
# <a name="custom-build-step-properties-linux-c"></a>Özel derleme adımı özellikleri (Linux C++)

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Özel derleme adımı tarafından yürütülecek komut. |
| Açıklama | Özel derleme adımı çalıştırıldığında görüntülenen ileti. |
| Çıkışlar | Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir. |
| Ek bağımlılıklar | Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi. |
| Önce yürütün ve yürütmeden önce yürütün | Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir. |
| Çıkışı İçerik Olarak Değerlendir | Bu seçenek yalnızca. appx paketindeki tüm içerik dosyalarını içeren Microsoft Store veya Windows Phone uygulamalar için anlamlıdır. |

::: moniker-end
