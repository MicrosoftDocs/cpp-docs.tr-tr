---
title: Derleyici Hatası C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: 81e2da31b39b323919132ae86cd365d9c119be32
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553523"
---
# <a name="compiler-error-c2415"></a>Derleyici Hatası C2415

işlenen türü uygun değil

Bu türündeki işlenenler opcode kullanmaz.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Opcode kullanılan işlenenler sayısını desteklemiyor. İşlenen doğru sayısını belirlemek için bir derleme dili başvurusu el ile denetleyin.

1. Daha yeni bir işlemci yönergesi ek türleri ile destekler. Ayarlama [/arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) daha sonraki bir işlemci kullanmak için seçeneği.