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
ms.workload: cplusplus
ms.openlocfilehash: 325a9a98ec536eaabedef3a93fbe38ccc2016cd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **__Pascal**, **__fortran**, ve **__syscall** çağırma kurallarını artık desteklenmemektedir. Uygun bağlayıcı seçenekleri ve desteklenen çağırma kurallarını birini kullanarak işlevleri taklit edebilir.  
  
 WINDOWS. H destekler **WINAPI** hedefi için uygun çağırma çevirir makrosu. Kullanım **WINAPI** önceden kullanıldığı **PASCAL** veya **__far \__pascal**.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)