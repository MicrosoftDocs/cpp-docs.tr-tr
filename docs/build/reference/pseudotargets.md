---
title: Sözde Hedefler
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
ms.openlocfilehash: 90552d00aaeed804f2bf492a94493882f196167d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824019"
---
# <a name="pseudotargets"></a>Sözde Hedefler

Bir pseudotarget bir bağımlılık satırda bir dosya adı yerine kullanılan bir etikettir. Bu yok ve bu nedenle, güncel olmayan bir dosya yorumlanır. NMAKE pseudotarget'ın zaman damgası tüm etkilenenleri en son olduğunu varsayar. Hiçbir bağımlıları varsa, geçerli zamanı varsayılır. Hedef olarak bir pseudotarget kullandıysanız, kendi komutları her zaman yürütülür. Bir bağlı kullanılan bir pseudotarget de bir hedef olarak başka bir bağımlılık olarak yer almalıdır. Ancak, bu bağımlılık komutları blok olması gerekmez.

Pseudotarget adları hedefler için dosya adı sözdizimi kurallarını izleyin. Ancak, bir uzantı adı yoksa (yani, bir nokta içermeyen), dosya adları için 8 karakter sınırı aşabilir ve en fazla 256 karakter uzunluğunda olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Hedefler](targets.md)
