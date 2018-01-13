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
ms.workload: cplusplus
ms.openlocfilehash: c05dcd516af5c078b4e4e664bae16f65370ca117
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Özel Durum İşleme için Veri Bırakma, Hata Ayıklayıcı Desteği](../build/unwind-data-for-exception-handling-debugger-support.md)