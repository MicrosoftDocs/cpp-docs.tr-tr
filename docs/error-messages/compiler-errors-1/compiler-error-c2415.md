---
title: Derleyici hatası C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: a0cdd528eca8ea267c62e6d44752d29ae16830c4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205627"
---
# <a name="compiler-error-c2415"></a>Derleyici hatası C2415

uygun olmayan işlenen türü

Opcode bu türdeki işlenenleri kullanmaz.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Opcode, kullanılan işlenen sayısını desteklemiyor. Doğru işlenen sayısını öğrenmek için bütünleştirilmiş kod dili başvurusu el ile denetleyin.

1. Daha yeni bir işlemci ek türler ile yönergeyi destekler. [/Arch (en düşük CPU mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) seçeneğini sonraki işlemciyi kullanacak şekilde ayarlayın.
