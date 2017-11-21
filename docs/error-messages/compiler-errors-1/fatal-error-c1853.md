---
title: "Önemli hata C1853 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1853
dev_langs: C++
helpviewer_keywords: C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23b5302428fc216a8349e8cf022c184caa57202c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1853"></a>Önemli hata C1853
  
> '*filename*' önceden derlenmiş üstbilgi dosyası Derleyici önceki bir sürümünden veya önceden derlenmiş üst bilgi C++ olduğu ve c (veya tersi) kullanıyorsanız  
  
Olası nedenler:  
  
-   Önceden derlenmiş üst bilgi, önceki bir derleyici sürümüyle derlendi. Geçerli derleyici üstbilgiyle yeniden derlenmesi deneyin.  
  
-   Önceden derlenmiş üst bilgi C++ ise ve c C ile kullanılmak üzere üstbilgi birini belirterek yeniden derlenmesi deneyin kullanıyorsanız [tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçenekleri veya "c" soneki kaynak dosyasının değiştirme. Daha fazla bilgi için bkz: [kodu önceden derlemek için iki seçenek](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).