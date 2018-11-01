---
title: 1.1 Kapsam
ms.date: 11/04/2016
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
ms.openlocfilehash: f87f631ae2d36662daa2ece4790170c00c5cbeb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449211"
---
# <a name="11-scope"></a>1.1 Kapsam

Bu belirtim burada görüntülerle kullanıcı derleyici ve çalışma zamanı sistemi tarafından program paralel olarak yürütmek için uygulanacak eylemleri açıkça belirtir, yalnızca kullanıcı yönlendirilmiş paralelleştirme kapsar. OpenMP C ve C++ uygulamaları bağımlılıkları, çakışmaları, kilitlenmeleri, yarış durumları veya yanlış programın yürütülmesine neden başka sorunlar olup olmadığını denetlemek için gerekli değildir. Kullanıcı, OpenMP C ve C++ API yapıları kullanarak uygulamanın düzgün çalıştığından emin sağlamaktan sorumludur. Derleyici tarafından oluşturulan otomatik paralelleştirme ve derleyici yönergeleri gibi paralelleştirme yardımcı olması için bu belgede ele alınmamaktadır.