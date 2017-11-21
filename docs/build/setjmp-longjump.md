---
title: setjmp longjump | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3617f70e7c62e1845d8d24e11cebdd7738c507f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setjmplongjump"></a>setjmp/longjump
Setjmpex.h ya da setjmp.h'ı eklediğinizde, tüm çağrılar [setjmp](../c-runtime-library/reference/setjmp.md) veya [longjmp](../c-runtime-library/reference/longjmp.md) yıkıcıları ve son çağrıları bırakmayla neden olur.  Bu x86 setjmp.h'ı son yan tümceleri de dahil olmak üzere burada ve değil çağrılan Yıkıcılar farklıdır.  
  
 Çağrı `setjmp` geçerli yığın işaretçisi, geçici olmayan Yazmaçları ve MxCsr yazmaçlar korur.  Çağrılar `longjmp` dönün en son `setjmp` site ve sıfırlar yığın işaretçisi, geçici olmayan Yazmaçları ve MxCsr kaydeder, duruma geri tarafından en son korunduğu çağrı `setjmp` çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma kuralı](../build/calling-convention.md)