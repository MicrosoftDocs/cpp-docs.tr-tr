---
title: "2.1 yönerge biçimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5760c4ccd3fcaf036f0d6d0aef09d29bbbaf8862
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="21-directive-format"></a>2.1 Yönerge Biçimi
OpenMP yönergesi sözdizimi resmi olarak dilbilgisi tarafından belirtilen [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)ve basit şekilde:  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 Her yönergesi ile başlayan **#pragma omp**, olası diğer (OpenMP olmayan veya satıcı uzantıları OpenMP) pragma yönergeleri aynı adı ile çakışıyor. Yönergesi kalanı derleyici yönergeleri C ve C++ standartları kuralları izler. Beyaz alan öncesinde ve sonrasında özel olarak, kullanılabilir  **#** , ve bir yönerge sözcükleri ayırmak için boşluk bazen kullanılmalıdır. Aşağıdaki belirteçleri ön işleme **#pragma omp** makro değiştirme tabi olan.  
  
 Yönergeleri büyük/küçük harfe duyarlıdır. Yan tümceleri yönergeleri görünme sırasını önemli değildir. Maddeleri hakkındaki yönergeleri, gerektiğinde her yan tümcesi açıklamasında listelenen kısıtlamalarına tabidir yinelenebilir. Varsa *değişken listesi* görünür bir yan tümcesinde yalnızca değişkenleri belirtmelisiniz. Yalnızca bir *yönergesi adı* yönergesi belirtilebilir.  Örneğin, aşağıdaki yönergesi izin verilmiyor:  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 OpenMP yönergesi yapılandırılmış bir blok olmalıdır en fazla bir izleyen ifadeyi için geçerlidir.