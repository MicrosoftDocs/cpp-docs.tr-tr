---
title: İşlevlerle Makrolar Arasında Seçim Önerileri
description: Microsoft C çalışma zamanı kitaplığı 'nda (CRT) makro vs işlevleri kullanma arasındaki farklılıkları açıklar.
ms.date: 11/04/2016
f1_keywords:
- c.functions
helpviewer_keywords:
- functions [CRT], vs. macros
- macros, vs. functions
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
ms.openlocfilehash: 8c47bf1924aeb94e2e4c9ee9358627cafcf90cba
ms.sourcegitcommit: a6b97f5d78299ad93675de2fe0f0561f528d26c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90569538"
---
# <a name="recommendations-for-choosing-between-functions-and-macros"></a>İşlevlerle Makrolar Arasında Seçim Önerileri

Microsoft çalışma zamanı kitaplığı yordamlarının çoğu derlenmiş veya birleştirilmiş işlevlerdir, ancak bazı yordamlar makro olarak uygulanır. Bir üst bilgi dosyası bir yordamın bir işlevini ve makro sürümünü bildiriyorsa, her zaman işlev bildiriminden sonra göründüğünden, makro tanımı öncelik kazanır. Hem bir işlev hem de makro olarak uygulanan bir yordamı çağırdığınızda, derleyicinin işlev sürümünü kullanmak için iki şekilde zorlayabilirsiniz:

- Yordamın adını parantez içine alın.

    ```C
    #include <ctype.h>
    a = _toupper(a);    // Use macro version of toupper.
    a = (_toupper)(a);  // Force compiler to use
                        // function version of toupper.
    ```

- Şu yönergeyle makro tanımını "tanımlayın" `#undef` :

    ```C
    #include <ctype.h>
    #undef _toupper
    ```

Bir kitaplık yordamının bir işlevi ve makro uygulamasıyla arasında seçim yapmanız gerekirse, aşağıdaki ticareti göz önünde bulundurun:

- **Hız ve boyut karşılaştırması** Makroları kullanmanın ana avantajı daha hızlı yürütme süresi olur. Ön işleme sırasında, bir makro her kullanıldığında (tanımına göre değiştirilmiştir) satır içi genişletilir. İşlev tanımı, kaç kez çağrıldığına bakılmaksızın yalnızca bir kez gerçekleşir. Makrolar kod boyutunu artırabilir, ancak işlev çağrılarıyla ilişkili ek yüke sahip değildir.

- **İşlev değerlendirmesi** Bir işlev bir adresi değerlendirir; makro değildir. Bu nedenle, bir işaretçi gerektiren bağlamlarda makro adı kullanamazsınız. Örneğin, bir işlev için bir işaretçi bildirebilirsiniz, ancak bir işaretçiye işaretçi ekleyebilirsiniz.

- **Tür denetimi** Bir işlevi bildirdiğinizde, derleyici bağımsız değişken türlerini denetleyebilir. Bir makro bildiremediği için, derleyici makro bağımsız değişken türlerini denetlemez; bir makroya geçirdiğiniz bağımsız değişkenlerin sayısını denetleyebilir ancak

## <a name="see-also"></a>Ayrıca bkz.

[Tür-genel matematik](tgmath.md)\
[CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)