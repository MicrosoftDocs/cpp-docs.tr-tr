---
title: 4. Ortam Değişkenleri
ms.date: 11/04/2016
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: 0dec302762ad22fc3c7f6691ef63df1b07d5940d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456608"
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