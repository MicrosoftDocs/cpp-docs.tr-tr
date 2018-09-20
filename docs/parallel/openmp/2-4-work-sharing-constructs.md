---
title: 2.4 iş paylaşım yapıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 719b33698b708761f0cd56e65a70a6ea8fa3b053
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411124"
---
# <a name="24-work-sharing-constructs"></a>2.4 İş Paylaşım Yapıları

Bir iş paylaşımı yapısı karşılaştığınızda takım üyeleri arasında ilişkili deyimin yürütme dağıtır. Yeni iş parçacıkları iş paylaşım yönergelerinin başlatılmaz ve girişi için bir iş paylaşımı yapısı zımni hiçbir engel yok.

Bir dizi iş paylaşım yapıları ve **engel** karşılaştı yönergeleri her iş parçacığında bir takım için aynı olması gerekir.

Aşağıdaki iş paylaşım yapıları OpenMP tanımlar ve bunlar aşağıdaki bölümlerde açıklanmıştır:

- **için** yönergesi

- **bölümler** yönergesi

- **tek** yönergesi