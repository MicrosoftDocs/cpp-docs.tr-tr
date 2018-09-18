---
title: Derleyici Hatası C2414 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2414
dev_langs:
- C++
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 642cb00605ed13146288edf5d39cb5d0c14c6e9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089924"
---
# <a name="compiler-error-c2414"></a>Derleyici Hatası C2414

geçersiz sayıda işlenen

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Opcode kullanılan işlenenler sayısını desteklemiyor. İşlenen doğru sayısını belirlemek için bir derleme dili başvurusu el ile denetleyin.

1. Daha yeni bir işlemci işlenenleri farklı sayıda talimatıyla destekler. Ayarlama [/arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) daha sonraki bir işlemci kullanmak için seçeneği.