---
title: "Kullanılmayan çağırma kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad065eb3f35080ff2e5743c0259b20ba72ee6175
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **__Pascal**, **__fortran**, ve **__syscall** çağırma kurallarını artık desteklenmemektedir. Uygun bağlayıcı seçenekleri ve desteklenen çağırma kurallarını birini kullanarak işlevleri taklit edebilir.  
  
 \<Windows.h > artık destekliyor **WINAPI** hedefi için uygun çağırma çevirir makrosu. Kullanım **WINAPI** önceden kullanıldığı **PASCAL** veya **__far \__pascal**.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)