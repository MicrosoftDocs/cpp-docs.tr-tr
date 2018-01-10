---
title: "Önemli hata C1047 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1047
dev_langs: C++
helpviewer_keywords: C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6ddc117d1e83c635bfbc644606c6c8c6032ff4f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1047"></a>Önemli hata C1047
Nesne veya kitaplık dosyası 'dosyası' diğer nesneleri daha eski bir derleyicisi ile oluşturulmuş; eski nesneler ve kitaplıkları yeniden derleme  
  
 Nesne dosyaları veya kitaplıkları ile yapılandırıldığında C1047 nedeni **/LTCG** birlikte, ancak bu nesne dosyaları veya kitaplıkları Visual C++ araç takımını farklı sürümlerini burada yerleşik bağlanır.  
  
 Derleyici yeni bir sürümünü kullanmaya başlamak, ancak varolan nesne dosyaları veya kitaplığı temiz bir yeniden oluşturma işlemi gerçekleştirmeyin bu durum oluşabilir.  
  
 C1047 çözmek için tüm nesne dosyaları veya kitaplıkları yeniden oluşturun.