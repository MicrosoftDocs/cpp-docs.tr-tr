---
title: Hazırlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69f1b7e131b614aa4714f0c2be19fab79982031c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108631"
---
# <a name="marshaling"></a>Hazırlama

Hazırlama COM tekniği nesneyi başka bir işlemde kullanılmak üzere bir işlem tarafından kullanıma sunulan arabirimleri sağlar. Hazırlama, COM kodu sağlar (veya arabirimi uygulayıcı tarafından sağlanan kodu kullanır) işlemleri arasında (yanı sıra, diğer makineler üzerinde çalışan işlemlere kablo üzerinden) taşınabilir bir biçime bir yöntemin parametre paketi ve bu parametreleri açmak için sonunda. Benzer şekilde, COM çağrısından dönüşte aynı adımları gerçekleştirmeniz gerekir.

> [!NOTE]
>  Nesne olarak aynı işlemde bir nesne tarafından sağlanan bir arabirimi kullanılırken hazırlama genellikle gerekli değildir. Ancak, hazırlama iş parçacıkları arasında gerekli olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Hazırlama ayrıntıları](/windows/desktop/com/marshaling-details)

