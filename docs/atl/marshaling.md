---
title: "Hazırlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f89b64794c50e381c07749984ce61579951fa02f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="marshaling"></a>Hazırlama
Hazırlama COM tekniği nesneyi başka bir işlemde kullanılacak bir işlem tarafından sunulan arabirimleri sağlar. Sıralama, COM kodu sağlar (veya arabirim uygulayıcıya tarafından sağlanan kod kullanır) işlemleri arasında (yanı sıra, diğer makinelerde çalışan işlemler için kablo üzerinden) taşınabilir bir biçime bir yöntemin parametre paketi ve bu parametrelerin açmak için sonunda. Benzer şekilde, COM çağrısından döndürülen aynı adımları gerçekleştirmeniz gerekir.  
  
> [!NOTE]
>  Nesne tarafından sağlanan bir arabirim nesne ile aynı işlemde kullanıldığında hazırlama genellikle gerekli değildir. Ancak, hazırlama iş parçacıkları arasında gerekli olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [Ayrıntılar hazırlama](http://msdn.microsoft.com/library/windows/desktop/ms692621)

