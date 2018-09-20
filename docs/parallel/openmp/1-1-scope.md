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
ms.openlocfilehash: 81babf799860030f6d398f64b55ed65039de8649
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393540"
---
# <a name="11-scope"></a>1.1 Kapsam

Bu belirtim burada görüntülerle kullanıcı derleyici ve çalışma zamanı sistemi tarafından program paralel olarak yürütmek için uygulanacak eylemleri açıkça belirtir, yalnızca kullanıcı yönlendirilmiş paralelleştirme kapsar. OpenMP C ve C++ uygulamaları bağımlılıkları, çakışmaları, kilitlenmeleri, yarış durumları veya yanlış programın yürütülmesine neden başka sorunlar olup olmadığını denetlemek için gerekli değildir. Kullanıcı, OpenMP C ve C++ API yapıları kullanarak uygulamanın düzgün çalıştığından emin sağlamaktan sorumludur. Derleyici tarafından oluşturulan otomatik paralelleştirme ve derleyici yönergeleri gibi paralelleştirme yardımcı olması için bu belgede ele alınmamaktadır.