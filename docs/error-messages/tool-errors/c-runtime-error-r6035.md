---
title: "C çalışma zamanı hatası R6035 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6035
dev_langs: C++
helpviewer_keywords: R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b5f9fb1f7562b26382c6b36e3947367013631bf
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="c-runtime-error-r6035"></a>C çalışma zamanı hatası R6035
Bu güvenlik tanımlama bilgisinde bağlı olan bir işlev etkinken Microsoft Visual C++ çalışma zamanı kitaplığı, hata R6035 - bu uygulamanın modülünde modülünün genel güvenlik tanımlama bilgisi başlatılıyor.  __Security_init_cookie önceki çağırın.  
  
 [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) genel güvenlik tanımlama bilgisi ilk kullanılmadan önce çağrılmalıdır.  
  
 Genel güvenlik tanımlama bilgisi ile derlenmiş kod taşması koruma için kullanılan [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ve yapılandırılmış özel durum işleme kullanan kod. Esas olarak, girişinde taşması korumalı işlevi için tanımlama bilgisi yığında yerleştirilir ve Çıkışta karşı genel tanımlama bilgisi değerini yığında karşılaştırılır. Aralarındaki fark, bir arabellek taşması oluştu ve program hemen sonlandırılması sonuçları gösterir.  
  
 Hata R6035 gösteren bir çağrı `__security_init_cookie` korumalı işlevi girildikten sonra yapıldı. Devam etmek için yürütme olsaydı, tanımlama bilgisi yığında artık genel tanımlama bilgisi eşleşir çünkü alacaklardır arabellek taşması algıladı.  
  
 Aşağıdaki DLL örneği göz önünde bulundurun. DLL giriş noktası için DllEntryPoint bağlayıcı ayarlanır [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md) seçeneği. Bu DLL çağırmanız gerekir böylece hangi genel güvenlik tanımlama bilgisi normalde başlatma CRT'ın başlatma atlar `__security_init_cookie`.  
  
```  
// Wrong way to call __security_init_cookie  
DllEntryPoint(...) {  
   DllInitialize();  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
  
void DllInitialize() {  
   __security_init_cookie();  
}  
```  
  
 Bu örnek, çünkü DllEntryPoint yapılandırılmış özel durum işleme kullanır ve bu nedenle arabellek taşmaları algılamak için güvenlik tanımlama bilgisi kullanır R6035 hatasına neden olur. DllInitialize adlı zaman, genel güvenlik tanımlama bilgisi zaten yığında konmuş.  
  
 Bu örnekte, doğru bir şekilde gösterilmiştir:  
  
```  
// Correct way to call __security_init_cookie  
DllEntryPoint(...) {  
   __security_init_cookie();  
   DllEntryHelper();  
}  
  
void DllEntryHelper() {  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
```  
  
 Bu durumda, DllEntryPoint arabellek taşmaları karşı korumalı olmayan (yerel dize arabellek yok sahiptir ve yapılandırılmış özel durum işleme kullanmayan); Bu nedenle güvenle çağırabilirsiniz `__security_init_cookie`. Ardından, korumalı bir yardımcı işlevini çağırır.  
  
> [!NOTE]
>  Hata iletisi R6035 x86 tarafından oluşturulan yalnızca CRT hata ayıklama ve yapılandırılmış özel durum işleme, ancak koşul için bir hata özel durum tüm formları yanı sıra, tüm platformlarda, C++ EH gibi işliyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Güvenlik derinlemesine denetler](http://go.microsoft.com/fwlink/p/?linkid=7260)