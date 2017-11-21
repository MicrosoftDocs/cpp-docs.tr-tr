---
title: "Kullanılmayan çağırma kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs: C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb6eafda669f4901db1259881fd2ed8cb995f559
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **__Pascal**, **__fortran**, ve **__syscall** çağırma kurallarını artık desteklenmemektedir. Uygun bağlayıcı seçenekleri ve desteklenen çağırma kurallarını birini kullanarak işlevleri taklit edebilir.  
  
 WINDOWS. H destekler **WINAPI** hedefi için uygun çağırma çevirir makrosu. Kullanım **WINAPI** önceden kullanıldığı **PASCAL** veya **__far \__pascal**.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)