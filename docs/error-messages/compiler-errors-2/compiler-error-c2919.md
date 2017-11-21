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
ms.openlocfilehash: a70b679d4add5fa4ad2904e3c0d103e1c8881280
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2919"></a>Derleyici Hatası C2919
'type': WinRT türü yayımlanan yüzeyine işleçler kullanılamaz  
  
 Windows çalışma zamanı tür sistemi bir türdeki yayımlanan yüzeyde işleci üye işlevleri desteklemiyor. Tüm diller işleci üye işlevleri tüketebileceği olmasıdır. C++ kodu aynı sınıfın veya derleme biriminde çağrılabilir üye işlevleri özel veya dahili işleci oluşturabilirsiniz.  
  
 Bu sorunu gidermek için ortak arabirimden işleci üye işlevi kaldırın veya bir adlandırılmış üye işlevine değiştirin. Örneğin, yerine, `operator==`, üye fonksiyonu ad `Equals`.