---
title: 1.1 kapsam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48d14ec722299a9ff72ad5bab0a68cde5e00d6ad
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686808"
---
# <a name="11-scope"></a>1.1 Kapsam
Bu belirtimi; burada görüntülerle kullanıcı programı paralel olarak yürütmek için derleyici ve çalışma zamanı sistem tarafından gerçekleştirilecek eylemleri açıkça belirtir, yalnızca kullanıcı yönlendirilmiş paralelleştirme kapsar. OpenMP C ve C++ uygulamaları bağımlılıkları, çakışmaları, kilitlenmeler, yarış durumları ya da yanlış program yürütülmesine neden diğer sorunlar olup olmadığını denetlemek için gerekli değildir. OpenMP C ve C++ API yapılarına kullanarak uygulamayı doğru şekilde çalıştığından emin sağlamak için kullanıcının sorumluluğundadır. Derleyicinin ürettiği otomatik paralelleştirme ve bu tür paralelleştirme yardımcı olmak için derleyici yönergeleri Bu belgede ele alınmamıştır.