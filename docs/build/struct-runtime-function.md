---
title: RUNTIME_FUNCTION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c2f28380d4a14cf7617653ede20468c45649a8b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379932"
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