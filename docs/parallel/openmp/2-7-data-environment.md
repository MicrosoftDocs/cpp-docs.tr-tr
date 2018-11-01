---
title: 2.7 Veri Ortamı
ms.date: 11/04/2016
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
ms.openlocfilehash: b65dfc7d7694b36ef4f89351579cd73e07ab537c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491980"
---
# <a name="27-data-environment"></a>2.7 Veri Ortamı

Bu bölüm, bir yönerge ve veri ortamı paralel bölgeleri yürütülmesi sırasında şu şekilde denetlemek için birkaç yan tümceleri sunar:

- A **threadprivate** yönergesi dosya kapsam, ad alanı kapsamında veya blok kapsamı statik değişkenleri bir iş parçacığına yerel hale getirmek için sağlanır (aşağıdaki bölüme bakın).

- Paralel veya iş paylaşım yapıları süresi boyunca değişkenlerin paylaşım öznitelikleri denetlemek için yönergeleri belirtilebilir yan tümceleri içinde açıklanmıştır [bölümü 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.