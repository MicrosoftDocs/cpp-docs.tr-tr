---
title: "İşlevlerle makrolar arasında seçim önerileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.functions
dev_langs: C++
helpviewer_keywords:
- functions [CRT], vs. macros
- macros, vs. functions
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6e10a2a2991f314d61bd8c2df22b59d7791b6c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recommendations-for-choosing-between-functions-and-macros"></a>İşlevlerle Makrolar Arasında Seçim Önerileri
Çoğu Microsoft çalışma zamanı kitaplığı yordamları derlenen veya İşlevler birleştirilen, ancak bazı yordamları makroları olarak uygulanır. Bir işlev ve bir yordam makrosu sürümü üstbilgi dosyası bildirir, her zaman sonra işlevi bildirimi göründüğünden makro tanımı, önceliklidir. Bir işlev ve makro uygulanan bir yordam çağırdığınızda, iki yolla işlev sürümü kullanmak için derleyicisi uygulayabilirsiniz:  
  
-   Rutin adı parantez içine alın.  
  
    ```  
    #include <ctype.h>  
    a = _toupper(a);    // Use macro version of toupper.  
    a = (_toupper)(a);  // Force compiler to use   
                        // function version of toupper.  
    ```  
  
-   "İle bir makro tanımı tanımlarını Kaldır" `#undef` yönergesi:  
  
    ```  
    #include <ctype.h>  
    #undef _toupper  
    ```  
  
 Bir işlev makrosu uygulama kitaplığı yordamının arasında seçim yapmanız gerekiyorsa, aşağıdaki dengelemeler göz önünde bulundurun:  
  
-   **Hızı boyutu karşı** makroları kullanmanın ana avantajı daha hızlı yürütme saattir. Ön işleme sırasında bir makrosu (tanımına tarafından değiştirilen) genişletilir satır içi her zaman kullanılır. Bir işlev tanımı kaç kez bağımsız olarak yalnızca bir kez çağrılır oluşur. Makroları kod boyutunu artırabilir, ancak işlev çağrıları ile ilgili ek yükü gerekmez.  
  
-   **İşlev değerlendirmesi** işlevi için bir adres değerlendirir; makro desteklemez. Bu nedenle bir işaretçi gerektiren bağlamlarda makrosu adı kullanamazsınız. Örneğin, bir işlev işaretçisi ancak makro işaretçisi değil bildirebilirsiniz.  
  
-   **Tür denetleme** bir işlev bildirirken derleyici bağımsız değişken türleri kontrol edebilirsiniz. Makro bildiremezsiniz olduğundan derleyici makrosu bağımsız değişken türleri iade edilemiyor; bağımsız değişken sayısı denetleyebilirsiniz rağmen bir makro geçirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)