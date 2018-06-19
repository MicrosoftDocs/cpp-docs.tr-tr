---
title: Satır içi derlemede C++ işlevlerini çağırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffbd8038d240bc2ab0240d172d914790b6ca02ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049629"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C++ İşlevlerini Çağırma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bir `__asm` blok yalnızca aşırı yüklenmemiş genel C++ işlevleri çağırabilir. Aşırı yüklenmiş bir genel C++ işlevi ya da C++ üye işlevi çağrısı, derleyici bir hata verir.  
  
 Ayrıca ile bildirilen tüm işlevleri çağırabilir **extern "C"** bağlantı. Böylece bir `__asm` tüm standart üstbilgi dosyaları için kitaplık işlevlerini bildirme çünkü C Kitaplık işlevleri çağırmak için C++ programı blokta **extern "C"** bağlantı.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)