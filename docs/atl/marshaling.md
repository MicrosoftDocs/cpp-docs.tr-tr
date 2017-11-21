---
title: "Hazırlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ec8c85606f0f0ef3de67a61181ead6537fde179e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="marshaling"></a>Hazırlama
Hazırlama COM tekniği nesneyi başka bir işlemde kullanılacak bir işlem tarafından sunulan arabirimleri sağlar. Sıralama, COM kodu sağlar (veya arabirim uygulayıcıya tarafından sağlanan kod kullanır) işlemleri arasında (yanı sıra, diğer makinelerde çalışan işlemler için kablo üzerinden) taşınabilir bir biçime bir yöntemin parametre paketi ve bu parametrelerin açmak için sonunda. Benzer şekilde, COM çağrısından döndürülen aynı adımları gerçekleştirmeniz gerekir.  
  
> [!NOTE]
>  Nesne tarafından sağlanan bir arabirim nesne ile aynı işlemde kullanıldığında hazırlama genellikle gerekli değildir. Ancak, hazırlama iş parçacıkları arasında gerekli olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [Ayrıntılar hazırlama](http://msdn.microsoft.com/library/windows/desktop/ms692621)

