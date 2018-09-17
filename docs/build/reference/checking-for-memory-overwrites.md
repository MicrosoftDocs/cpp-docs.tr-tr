---
title: Bellek üzerine yazmalar için denetleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 246f625e899016080662f27a5901962c1c62f1a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718659"
---
# <a name="checking-for-memory-overwrites"></a>Bellek Üzerine Yazmalarını Denetleme

Yığın işleme işlevi çağrısında bir erişim ihlali alırsanız, programınızı yığın bozdu mümkündür. Bu durumun yaygın bir belirtisi olabilir:

```
Access Violation in _searchseg
```

[_Heapchk](../../c-runtime-library/reference/heapchk.md) işlev, hem hata ayıklama ve yayın derlemeleri (yalnızca Windows NT) çalışma zamanı kitaplığı yığının bütünlüğünü doğrulamak için. Kullanabileceğiniz `_heapchk` kadar aynı şekilde `AfxCheckMemory` işlevi bir yığın üzerine yaz, örneğin yalıtmak için:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Şimdiye kadar bu işlev başarısız olursa, yalıtmak hangi noktada yığın bozulmuş gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)