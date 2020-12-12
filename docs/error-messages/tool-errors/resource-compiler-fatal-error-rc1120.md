---
description: 'Daha fazla bilgi edinin: kaynak derleyicisi önemli hatası RC1120'
title: Kaynak Derleyicisi Önemli Hatası RC1120
ms.date: 11/04/2016
f1_keywords:
- RC1120
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
ms.openlocfilehash: bc0c90bf5d8dd4290ab20369235c53fcd2c80182
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272038"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Kaynak Derleyicisi Önemli Hatası RC1120

bellek yetersiz, gereken sayıda bayt

Kaynak derleyicisi, yığınında sakladığı öğeler için depolama alanını tüketti. Genellikle bu, çok fazla sembol olmasının sonucudur.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Windows takas dosyası alanını arttırın. Takas dosyası alanını artırma hakkında daha fazla bilgi için bkz. Windows yardımında sanal bellek.

1. Gereksiz içerme dosyalarını, özellikle gereksiz `#define` öğeleri ve işlev prototiplerini kaldırın.

1. Geçerli dosyayı iki veya daha fazla dosyaya bölmek ve ayrı olarak derlemek.

1. Sistemde çalışan diğer programları veya sürücüleri kaldırın ve bu, önemli miktarda bellek tüketiyor olabilir.
