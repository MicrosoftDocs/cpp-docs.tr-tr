---
title: setjmp longjump | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55cf6a2503367777464f09f92e3e3614c3d9f11b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379841"
---
# <a name="setjmplongjump"></a>setjmp/longjump
Setjmpex.h ya da setjmp.h'ı eklediğinizde, tüm çağrılar [setjmp](../c-runtime-library/reference/setjmp.md) veya [longjmp](../c-runtime-library/reference/longjmp.md) yıkıcıları ve son çağrıları bırakmayla neden olur.  Bu x86 setjmp.h'ı son yan tümceleri de dahil olmak üzere burada ve değil çağrılan Yıkıcılar farklıdır.  
  
 Çağrı `setjmp` geçerli yığın işaretçisi, geçici olmayan Yazmaçları ve MxCsr yazmaçlar korur.  Çağrılar `longjmp` dönün en son `setjmp` site ve sıfırlar yığın işaretçisi, geçici olmayan Yazmaçları ve MxCsr kaydeder, duruma geri tarafından en son korunduğu çağrı `setjmp` çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralı](../build/calling-convention.md)