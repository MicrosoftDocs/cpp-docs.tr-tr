---
title: "Boş ve tanımlanmamış makrolar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee85d6959536d2845d7b6e6ccf7f07924e46143f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="null-and-undefined-macros"></a>Boş ve Tanımlanmamış Makrolar
Null dizeler boş ve tanımlanmamış makrolar genişletin, ancak boş bir dize tanımlanan bir makro ifadeleri önişlemde tanımlı olarak kabul edilir. Makro boş bir dize tanımlamak için hiçbir karakter boşluk ya da sekme sonra hariç eşittir (=) komut satırı veya komut dosyası ve boş bir dize veya tanımı çift tırnak işaretleri içine alın belirtin (""). Makro tanımsız için kullanmak **! UNDEF.** Daha fazla bilgi için bkz: [derleme görevleri dosyası önişleme yönergeleri](../build/makefile-preprocessing-directives.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE makrosu tanımlama](../build/defining-an-nmake-macro.md)