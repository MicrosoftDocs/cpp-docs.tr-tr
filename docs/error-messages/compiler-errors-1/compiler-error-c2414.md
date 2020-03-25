---
title: Derleyici hatası C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: fbe627a57e5defc499a4bc5d463e0bf33494acba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205666"
---
# <a name="compiler-error-c2414"></a>Derleyici hatası C2414

geçersiz sayıda işlenen

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Opcode, kullanılan işlenen sayısını desteklemiyor. Doğru işlenen sayısını öğrenmek için bütünleştirilmiş kod dili başvurusu el ile denetleyin.

1. Daha yeni bir işlemci, farklı sayıda işleneni olan yönergeyi destekler. [/Arch (en düşük CPU mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) seçeneğini sonraki işlemciyi kullanacak şekilde ayarlayın.
