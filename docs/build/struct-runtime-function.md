---
title: RUNTIME_FUNCTION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 476ce4ad532f1e02b8863e2276fe0300c5895270
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="struct-runtimefunction"></a>struct RUNTIME_FUNCTION
Tablo tabanlı özel durum işleme yığın alanı ayırmak veya başka bir işlevi (örneğin, yaprak olmayan işlevler) tüm işlevler için bir tablo girişi gerektirir. İşlev tablosu girdileri biçime sahiptir:  
  
|||  
|-|-|  
|ULONG|Başlangıç adresi işlevi|  
|ULONG|İşlev bitiş adresi|  
|ULONG|Bırakma bilgisi adresi|  
  
 RUNTIME_FUNCTION yapısını bellekte DWORD hizalanmış olmalıdır. Tüm adresler resim görelidir, diğer bir deyişle, 32-bit uzaklıkları işlevi tablo girişi içeren görüntünün başlangıç adresinden oldukları. Bu girişler sıralanır ve bir PE32 + resminin ve.xdata'yı bölümünde yerleştirin. [JIT derleyiciler] dinamik olarak üretilen işlevler için bu işlevleri desteklemek için çalışma zamanı ya da RtlInstallFunctionTableCallback ya da RtlAddFunctionTable işletim sistemi için bu bilgileri sağlamak için kullanmalısınız. Bunu yapmak için hata işleme ve hata ayıklama işlemleri güvenilir olmayan istisna neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri bırakma, özel durum işleme için hata ayıklayıcı desteği](../build/unwind-data-for-exception-handling-debugger-support.md)