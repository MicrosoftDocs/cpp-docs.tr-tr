---
title: "Satır içi derlemede C++ işlevlerini çağırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c91829eac3247255d8fe3cb966a61fca5319f94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C++ İşlevlerini Çağırma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bir `__asm` blok yalnızca aşırı yüklenmemiş genel C++ işlevleri çağırabilir. Aşırı yüklenmiş bir genel C++ işlevi ya da C++ üye işlevi çağrısı, derleyici bir hata verir.  
  
 Ayrıca ile bildirilen tüm işlevleri çağırabilir **extern "C"** bağlantı. Böylece bir `__asm` tüm standart üstbilgi dosyaları için kitaplık işlevlerini bildirme çünkü C Kitaplık işlevleri çağırmak için C++ programı blokta **extern "C"** bağlantı.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır içi derleyicisi](../../assembler/inline/inline-assembler.md)