---
title: Derleyici Hatası C2919 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2919
dev_langs:
- C++
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5e2eb2a32f1a906814f5b347ba1ebf13eba71ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2919"></a>Derleyici Hatası C2919
'type': WinRT türü yayımlanan yüzeyine işleçler kullanılamaz  
  
 Windows çalışma zamanı tür sistemi bir türdeki yayımlanan yüzeyde işleci üye işlevleri desteklemiyor. Tüm diller işleci üye işlevleri tüketebileceği olmasıdır. C++ kodu aynı sınıfın veya derleme biriminde çağrılabilir üye işlevleri özel veya dahili işleci oluşturabilirsiniz.  
  
 Bu sorunu gidermek için ortak arabirimden işleci üye işlevi kaldırın veya bir adlandırılmış üye işlevine değiştirin. Örneğin, yerine, `operator==`, üye fonksiyonu ad `Equals`.