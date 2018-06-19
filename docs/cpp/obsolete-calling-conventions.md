---
title: Kullanılmayan çağırma kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d2a6188cf9d8c8283a6c03a2ca6c701e28baf0d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419852"
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **__Pascal**, **__fortran**, ve **__syscall** çağırma kurallarını artık desteklenmemektedir. Uygun bağlayıcı seçenekleri ve desteklenen çağırma kurallarını birini kullanarak işlevleri taklit edebilir.  
  
 \<Windows.h > artık destekliyor **WINAPI** hedefi için uygun çağırma çevirir makrosu. Kullanım **WINAPI** önceden kullanıldığı **PASCAL** veya **__far \__pascal**.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)