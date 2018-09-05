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
ms.openlocfilehash: 5185b3b39ad74381113bd858f9db20ccddfe0fa8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752605"
---
# <a name="recommendations-for-choosing-between-functions-and-macros"></a>İşlevlerle Makrolar Arasında Seçim Önerileri
Çoğu Microsoft çalışma zamanı kitaplık yordamları derlenmiş veya işlevleri bir araya getirilen, ancak bazı yordamları makroları olarak uygulanır. Bir üstbilgi dosyası hem işlev hem de bir yordam makrosu sürümünü bildirir, işlev bildiriminden sonra her zaman görünür olduğundan Makro tanımında, önceliklidir. Bir işlev ve makro uygulanan bir yordamı çağırdığınızda, derleyicinin iki yolla işlev sürümünü kullanmasını zorunlu kılabilirsiniz:  
  
-   Rutin adı ayraç içine alın.  
  
    ```C
    #include <ctype.h>  
    a = _toupper(a);    // Use macro version of toupper.  
    a = (_toupper)(a);  // Force compiler to use   
                        // function version of toupper.  
    ```  
  
-   "İle Makro tanımında Kaldır" `#undef` yönergesi:  
  
    ```C
    #include <ctype.h>  
    #undef _toupper  
    ```  
  
Bir yordamı makrosu uygulamasıdır ve bir işlev arasında seçim yapmanız gerekiyorsa, aşağıdaki stillerden göz önünde bulundurun:  
  
-   **Boyutu ve hızlı** makroları kullanmanın ana avantajı daha hızlı yürütme süresi kısadır. Ön işleme sırasında bir makro (tanımı tarafından değiştirilen) genişletilir satır içi kullanıldığı her zaman. Bir işlev tanımı, kaç kez bağımsız olarak yalnızca bir kez çağrılır gerçekleşir. Makrolar kod boyutunu artırabilir, ancak işlev çağrıları ile ilgili ek yükü izniniz yok.  
  
-   **İşlev değerlendirmesi** bir işlev bir adres olarak değerlendirilen; bir makro desteklemez. Bu nedenle, bir işaretçi gerektiren bağlamlarda makro adı kullanamazsınız. Örneğin, bir işlev işaretçisi, ancak bir makro işaretçisi değil bildirebilirsiniz.  
  
-   **Tür denetleme** bir işlev bildirdiğinizde, derleyici bağımsız değişken türlerini kontrol edebilirsiniz. Derleyici, makro bağımsız değişken türleri iade edilemedi, bir makro bildiremezsiniz çünkü değil; bağımsız değişken sayısı kontrol edebilirsiniz ancak bir makro geçirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)