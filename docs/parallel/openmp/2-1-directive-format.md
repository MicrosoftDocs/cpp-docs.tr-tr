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
ms.openlocfilehash: 1eec5a2f0e91df6e8d71797199bd3a3911a3aab0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687279"
---
# <a name="21-directive-format"></a>2.1 Yönerge Biçimi
OpenMP yönergesi sözdizimi resmi olarak dilbilgisi tarafından belirtilen [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)ve basit şekilde:  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 Her yönergesi ile başlayan **#pragma omp**, olası diğer (OpenMP olmayan veya satıcı uzantıları OpenMP) pragma yönergeleri aynı adı ile çakışıyor. Yönergesi kalanı derleyici yönergeleri C ve C++ standartları kuralları izler. Beyaz alan öncesinde ve sonrasında özel olarak, kullanılabilir **#**, ve bir yönerge sözcükleri ayırmak için boşluk bazen kullanılmalıdır. Aşağıdaki belirteçleri ön işleme **#pragma omp** makro değiştirme tabi olan.  
  
 Yönergeleri büyük/küçük harfe duyarlıdır. Yan tümceleri yönergeleri görünme sırasını önemli değildir. Maddeleri hakkındaki yönergeleri, gerektiğinde her yan tümcesi açıklamasında listelenen kısıtlamalarına tabidir yinelenebilir. Varsa *değişken listesi* görünür bir yan tümcesinde yalnızca değişkenleri belirtmelisiniz. Yalnızca bir *yönergesi adı* yönergesi belirtilebilir.  Örneğin, aşağıdaki yönergesi izin verilmiyor:  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 OpenMP yönergesi yapılandırılmış bir blok olmalıdır en fazla bir izleyen ifadeyi için geçerlidir.