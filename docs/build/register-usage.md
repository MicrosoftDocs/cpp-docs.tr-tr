---
title: YAZMAÇ kullanımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ce58e2cf-afd3-4068-980e-28a209298265
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6792fcf035ee698767c9dd099cb7b84f5b784616
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="register-usage"></a>Yazmaç Kullanımı
[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 16 XMM/YMM yazmaçlar kayan nokta kullanılabilir yanı sıra 16 genel amaçlı kayıtları (tamsayı kayıtları olarak bundan böyle olarak adlandırılır) mimarisi sağlar. Geçici kayıtları çağrıyla yok edilmesi için çağıran tarafından karalama kayıtlardır. Kalıcı Yazmaçları değerlerine bir işlev aramasıyla korumak için gereklidir ve kullanılırsa Aranan tarafından kaydedilmesi gerekir.  
  
 Aşağıdaki tabloda, her kayıt işlev çağrıları arasında nasıl kullanıldığı açıklanmaktadır:  
  
||||  
|-|-|-|  
|Yazmaç|Durum|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|RAX|Volatile|Dönüş değeri kaydı|  
|RCX|Volatile|İlk tamsayı bağımsız değişken|  
|RDX|Volatile|İkinci tamsayı bağımsız değişken|  
|R8|Volatile|Üçüncü bağımsız değişken|  
|R9|Volatile|Dördüncü tamsayı bağımsız değişken|  
|R10:R11|Volatile|Çağıran tarafından gerektiği şekilde korunmalıdır; syscall/sysret yönergelerinde kullanılmalıdır|  
|R12:R15|Kalıcı|Aranan tarafından korunmalıdır|  
|RDI|Kalıcı|Aranan tarafından korunmalıdır|  
|RSI|Kalıcı|Aranan tarafından korunmalıdır|  
|RBX|Kalıcı|Aranan tarafından korunmalıdır|  
|RBP|Kalıcı|Çerçeve işaretçisi olarak kullanılabilir; Aranan tarafından korunmalıdır|  
|RSP|Kalıcı|Yığın işaretçisi|  
|XMM0, YMM0|Volatile|İlk FP bağımsız değişkeni; ilk vektör tür bağımsız değişkeni olduğunda `__vectorcall` kullanılır|  
|XMM1, YMM1|Volatile|İkinci FP bağımsız değişkeni; İkinci vektör tür bağımsız değişkeni olduğunda `__vectorcall` kullanılır|  
|XMM2, YMM2|Volatile|Üçüncü FP bağımsız değişkeni; Üçüncü vektör tür bağımsız değişkeni olduğunda `__vectorcall` kullanılır|  
|XMM3, YMM3|Volatile|Dördüncü FP bağımsız değişkeni; Dördüncü vektör tür bağımsız değişkeni olduğunda `__vectorcall` kullanılır|  
|XMM4, YMM4|Volatile|Çağıran tarafından gerektiği şekilde korunmalıdır; Beşinci vektör tür bağımsız değişkeni olduğunda `__vectorcall` kullanılır|  
|XMM5, YMM5|Volatile|Çağıran tarafından gerektiği şekilde korunmalıdır; Altıncı vektör tür bağımsız değişkeni olduğunda `__vectorcall` kullanılır|  
|XMM6:XMM15, YMM6:YMM15|Kalıcı (XMM) Volatile (YMM üst kısmında)|Aranan tarafından korunması gerekir. YMM kayıtları, çağıran tarafından gerektiği şekilde korunmalıdır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x64 yazılım kuralları](../build/x64-software-conventions.md)   
 [__vectorcall](../cpp/vectorcall.md)
