---
title: 2.7 veri ortamı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1b0f253ce14ffc5d3740e582a9a51feea56ad32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="27-data-environment"></a>2.7 Veri Ortamı
Bu bölüm bir yönerge ve veri ortamı gibi paralel bölgeler, yürütme sırasında denetleme birkaç yan tümceleri sunar:  
  
-   A **threadprivate** yönergesi dosya kapsamı, ad alanı kapsamı veya statik blok kapsamı değişkenleri bir iş parçacığı yerel yapmak için sağlanır (aşağıdaki bölüme bakın).  
  
-   Paralel veya iş paylaşım yapıları süresince değişkenleri paylaşım özniteliklerini denetlemek için yönergeleri üzerinde belirtilebilir yan tümceleri içinde açıklanmıştır [bölüm 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.