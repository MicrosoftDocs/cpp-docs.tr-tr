---
title: setjmp longjump | Microsoft Docs
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
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 744b855d1b867507b54973f17e2a4f98b63e2b67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setjmplongjump"></a>setjmp/longjump
Setjmpex.h ya da setjmp.h'ı eklediğinizde, tüm çağrılar [setjmp](../c-runtime-library/reference/setjmp.md) veya [longjmp](../c-runtime-library/reference/longjmp.md) yıkıcıları ve son çağrıları bırakmayla neden olur.  Bu x86 setjmp.h'ı son yan tümceleri de dahil olmak üzere burada ve değil çağrılan Yıkıcılar farklıdır.  
  
 Çağrı `setjmp` geçerli yığın işaretçisi, geçici olmayan Yazmaçları ve MxCsr yazmaçlar korur.  Çağrılar `longjmp` dönün en son `setjmp` site ve sıfırlar yığın işaretçisi, geçici olmayan Yazmaçları ve MxCsr kaydeder, duruma geri tarafından en son korunduğu çağrı `setjmp` çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralı](../build/calling-convention.md)