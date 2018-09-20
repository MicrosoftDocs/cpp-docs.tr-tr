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
ms.openlocfilehash: 17c60c621defa15c034f57d0af8f14637db54f03
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378143"
---
# <a name="27-data-environment"></a>2.7 Veri Ortamı

Bu bölüm, bir yönerge ve veri ortamı paralel bölgeleri yürütülmesi sırasında şu şekilde denetlemek için birkaç yan tümceleri sunar:

- A **threadprivate** yönergesi dosya kapsam, ad alanı kapsamında veya blok kapsamı statik değişkenleri bir iş parçacığına yerel hale getirmek için sağlanır (aşağıdaki bölüme bakın).

- Paralel veya iş paylaşım yapıları süresi boyunca değişkenlerin paylaşım öznitelikleri denetlemek için yönergeleri belirtilebilir yan tümceleri içinde açıklanmıştır [bölümü 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.