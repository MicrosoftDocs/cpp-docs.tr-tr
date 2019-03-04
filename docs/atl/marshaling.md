---
title: Hazırlama
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 0661a4cdde0a3a875cf27221e884f6c65b9fea55
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269688"
---
# <a name="marshaling"></a>Hazırlama

Hazırlama COM tekniği nesneyi başka bir işlemde kullanılmak üzere bir işlem tarafından kullanıma sunulan arabirimleri sağlar. Hazırlama, COM kodu sağlar (veya arabirimi uygulayıcı tarafından sağlanan kodu kullanır) işlemleri arasında (yanı sıra, diğer makineler üzerinde çalışan işlemlere kablo üzerinden) taşınabilir bir biçime bir yöntemin parametre paketi ve bu parametreleri açmak için sonunda. Benzer şekilde, COM çağrısından dönüşte aynı adımları gerçekleştirmeniz gerekir.

> [!NOTE]
>  Nesne olarak aynı işlemde bir nesne tarafından sağlanan bir arabirimi kullanılırken hazırlama genellikle gerekli değildir. Ancak, hazırlama iş parçacıkları arasında gerekli olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Hazırlama ayrıntıları](/windows/desktop/com/marshaling-details)
