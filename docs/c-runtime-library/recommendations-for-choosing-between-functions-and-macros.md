---
title: İşlevlerle makrolar arasında seçim önerileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.functions
dev_langs:
- C++
helpviewer_keywords:
- functions [CRT], vs. macros
- macros, vs. functions
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4577ac1a0e1cac90a3436809722978d119c6b557
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)