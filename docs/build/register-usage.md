---
title: YAZMAÇ kullanımı
ms.date: 11/04/2016
ms.assetid: ce58e2cf-afd3-4068-980e-28a209298265
ms.openlocfilehash: fa04318ad4af298f300fbbbad8c01d0df9500ec7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629989"
---
# <a name="register-usage"></a>YAZMAÇ kullanımı

16 XMM/YMM yanı sıra 16 genel amaçlı kayıtları (tamsayı kayıtları olarak bundan sonra anılacaktır) mimarisi sunar x64 kayan nokta kullanıma kaydeder. Geçici kayıtları çağrıyla yok edilecek çağıran tarafından karalama kayıtlardır. Kalıcı kayıtlar arasında bir işlev çağrısı değerlerini korumak için gereklidir ve Aranan tarafından kullanılan kaydedilmesi gerekir.

## <a name="register-volatility-and-preservation"></a>Kayıt geçiciliğine ve korunması

Aşağıdaki tabloda, her kaydın işlev çağrıları arasında nasıl kullanıldığını açıklar:

||||
|-|-|-|
|Yazmaç|Durum|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|RAX'DAKİ|Volatile|Dönüş değeri kaydı|
|RCX|Volatile|İlk tamsayı bağımsız değişkeni|
|RDX|Volatile|İkinci bağımsız değişken|
|R8|Volatile|Üçüncü bağımsız değişken|
|R9|Volatile|Dördüncü tamsayı bağımsız değişkeni|
|R10:R11|Volatile|Çağıran tarafından gerektiği şekilde korunması gerekir; syscall/sysret yönergelerinde kullanılmalıdır|
|R12:R15|Kalıcı|Aranan tarafından korunması gerekir|
|RDI|Kalıcı|Aranan tarafından korunması gerekir|
|RSI|Kalıcı|Aranan tarafından korunması gerekir|
|RBX|Kalıcı|Aranan tarafından korunması gerekir|
|RBP|Kalıcı|Çerçeve işaretçisi olarak kullanılabilir. Aranan tarafından korunması gerekir|
|RSP|Kalıcı|Yığın işaretçisi|
|XMM0, YMM0|Volatile|İlk FP bağımsız değişkeni; ilk vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM1'DE, YMM1|Volatile|İkinci FP bağımsız değişkeni; vektör türü bağımsız değişken ikinci zaman `__vectorcall` kullanılır|
|XMM2, YMM2|Volatile|Üçüncü FP bağımsız değişkeni; Üçüncü vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM3, YMM3|Volatile|Dördüncü FP bağımsız değişkeni; Dördüncü vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM4, YMM4|Volatile|Çağıran tarafından gerektiği şekilde korunması gerekir; Beşinci vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM5, YMM5 ARASINDA|Volatile|Çağıran tarafından gerektiği şekilde korunması gerekir; Altıncı vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM6:XMM15, YMM6:YMM15|Kalıcı (XMM) Volatile (YMM üst kısmında)|Aranan tarafından korunmalıdır. YMM kayıtları, çağıran tarafından gerektiği şekilde korunmalıdır.|

İşlev çıkmadan ve C çalışma zamanı kitaplığı çağrıları ve Windows sistem çağrıları işlev girişi, CPU yön bayrağı bayrakları kayıt temizlenmesi bekleniyor.

## <a name="see-also"></a>Ayrıca bkz.

- [x64 Yazılım Kuralları](../build/x64-software-conventions.md)
- [__vectorcall](../cpp/vectorcall.md)
- [Yön bayrağı](../c-runtime-library/direction-flag.md)
