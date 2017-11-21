---
title: "Yapı içi değerler ve satır içi derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c60932b719b25365c7d8f65a4649ef782a4f9888
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="intrinsics-and-inline-assembly"></a>Yapı İçi Değerler ve Satır İçi Derleme
Kısıtlamalarını birini [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] derleyici hiçbir satır içi derleyici desteğine sahip etmektir. İşlevler, bunun anlamı C veya C++ ya da alt yordamlar veya iç işlevler derleyici tarafından desteklenen olarak yazılması gerekir yazılamaz. Diğerleri değildir bazı önemli performans işlevlerdir. Başarım duyarlı işlevler iç işlev olarak uygulanmalıdır.  
  
 Derleyici tarafından desteklenen iç bilgileri açıklanan [derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x64 yazılım kuralları](../build/x64-software-conventions.md)