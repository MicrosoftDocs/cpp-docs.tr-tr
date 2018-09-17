---
title: Sözde hedefler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56c0c0c93163759b604352a6e623f15726b8e7ec
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715838"
---
# <a name="pseudotargets"></a>Sözde Hedefler

Bir pseudotarget bir bağımlılık satırda bir dosya adı yerine kullanılan bir etikettir. Bu yok ve bu nedenle, güncel olmayan bir dosya yorumlanır. NMAKE pseudotarget'ın zaman damgası tüm etkilenenleri en son olduğunu varsayar. Hiçbir bağımlıları varsa, geçerli zamanı varsayılır. Hedef olarak bir pseudotarget kullandıysanız, kendi komutları her zaman yürütülür. Bir bağlı kullanılan bir pseudotarget de bir hedef olarak başka bir bağımlılık olarak yer almalıdır. Ancak, bu bağımlılık komutları blok olması gerekmez.

Pseudotarget adları hedefler için dosya adı sözdizimi kurallarını izleyin. Ancak, bir uzantı adı yoksa (yani, bir nokta içermeyen), dosya adları için 8 karakter sınırı aşabilir ve en fazla 256 karakter uzunluğunda olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Hedefler](../build/targets.md)