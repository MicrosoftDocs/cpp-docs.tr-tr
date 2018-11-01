---
title: Derleyici Hatası C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: 84fa715c8bd567770f361552e203a37c44ffdde4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451057"
---
# <a name="compiler-error-c2414"></a>Derleyici Hatası C2414

geçersiz sayıda işlenen

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Opcode kullanılan işlenenler sayısını desteklemiyor. İşlenen doğru sayısını belirlemek için bir derleme dili başvurusu el ile denetleyin.

1. Daha yeni bir işlemci işlenenleri farklı sayıda talimatıyla destekler. Ayarlama [/arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) daha sonraki bir işlemci kullanmak için seçeneği.