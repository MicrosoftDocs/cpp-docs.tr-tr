---
title: "Derleyici Hatası C2919 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2919
dev_langs: C++
helpviewer_keywords: C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e2bde12c4c6ffa94f55e9dd205c3132a755ad94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2919"></a>Derleyici Hatası C2919
'type': WinRT türü yayımlanan yüzeyine işleçler kullanılamaz  
  
 Windows çalışma zamanı tür sistemi bir türdeki yayımlanan yüzeyde işleci üye işlevleri desteklemiyor. Tüm diller işleci üye işlevleri tüketebileceği olmasıdır. C++ kodu aynı sınıfın veya derleme biriminde çağrılabilir üye işlevleri özel veya dahili işleci oluşturabilirsiniz.  
  
 Bu sorunu gidermek için ortak arabirimden işleci üye işlevi kaldırın veya bir adlandırılmış üye işlevine değiştirin. Örneğin, yerine, `operator==`, üye fonksiyonu ad `Equals`.