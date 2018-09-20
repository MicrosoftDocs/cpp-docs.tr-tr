---
title: 2.1 yönerge biçimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b2f2d2f5742dbc4faa1d8386e935c9d4ccc8049
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424657"
---
# <a name="21-directive-format"></a>2.1 Yönerge Biçimi

Bir OpenMP yönergesi sözdizimi resmi dilbilgisi tarafından belirtilen [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)ve resmi olmayan adı şu şekilde:

```
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

Her yönerge ile başlayan **#pragma omp**, aynı ada sahip diğer (OpenMP olmayan ya da satıcı uzantıları için OpenMP) pragma yönergeleri ile Çakışma olasılığını azaltmak için. Yönerge geri kalanında derleyici yönergeleri C ve C++ standartları kurallarını izler. Önce ve sonra boşluk özellikle kullanılabilir **#**, ve bir yönergesi içinde sözcükleri ayırmak için boşluk bazen kullanılmalıdır. Ön işleme belirteci aşağıdaki **#pragma omp** Makro değişikliği tabi olan.

Yönergeleri büyük/küçük harfe duyarlıdır. Yan tümceleri yönergelerinde görünme sırası önemli değildir. Şirket yönergeleri yan tümceleri, gerektiğinde her bir yan tümceye açıklamasında listelenen kısıtlamalarla tabi yinelenebilir. Varsa *değişken listesi* görünür bir yan tümcesinde, yalnızca değişkenleri belirtmeniz gerekir. Yalnızca bir *yönergesi adı* yönerge başına belirtilebilir.  Örneğin, aşağıdaki yönerge izin verilmiyor:

```
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

Bir OpenMP yönergesinde yapısal bloğunun olmalıdır en fazla bir sonraki deyimi için geçerlidir.