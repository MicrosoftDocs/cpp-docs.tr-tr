---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2415'
title: Derleyici hatası C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: 21bbeabe0a5eacea55d2a38ab515429e6468ba57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340352"
---
# <a name="compiler-error-c2415"></a>Derleyici hatası C2415

uygun olmayan işlenen türü

Opcode bu türdeki işlenenleri kullanmaz.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Opcode, kullanılan işlenen sayısını desteklemiyor. Doğru işlenen sayısını öğrenmek için bütünleştirilmiş kod dili başvurusu el ile denetleyin.

1. Daha yeni bir işlemci ek türler ile yönergeyi destekler. [/Arch (en düşük CPU mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) seçeneğini sonraki işlemciyi kullanacak şekilde ayarlayın.
