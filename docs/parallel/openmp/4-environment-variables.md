---
title: 4. Ortam değişkenlerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aec56dad334dcd27de2068e660ff8ec5a6e72f90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415505"
---
# <a name="4-environment-variables"></a>4. Ortam Değişkenleri

OpenMP C ve C++ API ortam değişkenlerini (veya eşdeğer bir platforma özgü mekanizmaları) Bu bölümde açıklanmaktadır paralel kod yürütme denetimi.  Ortam değişkenlerinin adları büyük olmalıdır. Atanmış değerleri büyük/küçük harfe duyarsızdır ve öndeki ve sondaki boşluk olabilir.  Değerlerin program başlatıldıktan sonra yapılan değişiklikler yok sayılır.

Ortam değişkenleri aşağıdaki gibidir:

- **OMP_SCHEDULE** çalışma zamanı zamanlama türü ve öbek boyutunu ayarlar.

- **OMP_NUM_THREADS** yürütme sırasında kullanılacak iş parçacığı sayısını ayarlar.

- **Omp_dynamıc** etkinleştirir veya iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakır.

- **OMP_NESTED** etkinleştirir veya iç içe geçmiş paralellik devre dışı bırakır.

Bu bölümdeki örnekler, yalnızca bu değişkenleri UNIX C Kabuğu (csh) ortamlarda nasıl ayarlanabilir gösterir. Korn içinde kabuk ve DOS ortamları eylemleri benzer, aşağıdaki gibidir:

csh: setenv OMP_SCHEDULE "dinamik"

ksh: OMP_SCHEDULE dışarı aktarma "dinamik" =

DOS: OMP_SCHEDULE Ayarla "dinamik" =