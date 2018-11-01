---
title: Kullanılmayan Çağırma Kuralları
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 86c75c779158d9f191dd015410cf16c9ce25690d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587999"
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları

## <a name="microsoft-specific"></a>Microsoft'a Özgü

**__Pascal**, **__fortran**, ve **__syscall** çağırma kuralları artık desteklenmiyor. Uygun bağlayıcı seçenekleri ve desteklenen çağırma kuralları birini kullanarak işlevlerini taklit edebilir.

\<Windows.h > artık hedef uygun çağırma kuralının izlendiği WINAPI makrosu destekler. Burada daha önce kullandığınız PASCAL WINAPI kullanın veya **__far \__pascal**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)