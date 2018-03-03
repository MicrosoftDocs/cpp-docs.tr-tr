---
title: "Satır içi derlemede C++ işlevlerini çağırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a805d3bd22b55dd41d7221e970f0557855e4544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C++ İşlevlerini Çağırma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bir `__asm` blok yalnızca aşırı yüklenmemiş genel C++ işlevleri çağırabilir. Aşırı yüklenmiş bir genel C++ işlevi ya da C++ üye işlevi çağrısı, derleyici bir hata verir.  
  
 Ayrıca ile bildirilen tüm işlevleri çağırabilir **extern "C"** bağlantı. Böylece bir `__asm` tüm standart üstbilgi dosyaları için kitaplık işlevlerini bildirme çünkü C Kitaplık işlevleri çağırmak için C++ programı blokta **extern "C"** bağlantı.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)