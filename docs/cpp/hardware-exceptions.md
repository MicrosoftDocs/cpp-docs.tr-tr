---
title: Donanım Özel Durumları
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [C++], hardware
- errors [C++], low-level
- errors [C++], hardware
- hardware exceptions [C++]
- low level errors
ms.assetid: 06ac6f01-a8cf-4426-bb12-1688315ae1cd
ms.openlocfilehash: 17775f3b2ee6dfa235c93d0bf0e3335b464aaa69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153677"
---
# <a name="hardware-exceptions"></a>Donanım Özel Durumları

İşletim sistemi tarafından kabul edilen standart özel durumların çoğu, donanım tarafından tanımlanmış özel durumlardır. Windows, birkaç alt düzey yazılım özel durumunu tanır, ancak bunlar genellikle en iyi işletim sistemi tarafından ele alınır.

Windows, farklı işlemcilerin donanım hatalarını bu bölümdeki özel durum kodlarıyla eşleştirir. Bazı durumlarda, bir işlemci bu özel durumların yalnızca alt kümesini oluşturabilir. Windows, özel durum hakkındaki bilgileri önceden işler ve uygun özel durum kodunu verir.

Windows tarafından tanınan donanım özel durumları, aşağıdaki tabloda özetlenmiştir:

|Özel durum kodu|Özel durum nedeni|
|--------------------|------------------------|
|STATUS_ACCESS_VIOLATION|Erişilemeyen bellek konumu okunuyor veya bu konuma yazılıyor.|
|STATUS_BREAKPOINT|Donanım tarafından tanımlanmış bir kesme noktasıyla karşılaşıldı; yalnızca hata ayıklayıcılar tarafından kullanılır.|
|STATUS_DATATYPE_MISALIGNMENT|Düzgün bir şekilde hizalanmamış bir adreste veriler okunuyor veya yazılıyor; örneğin, 16 bit varlıklar 2 bayt sınırlarda hizalanmalıdır. (Intel 80 uygulanamaz*x*86 işlemcileri.)|
|STATUS_FLOAT_DIVIDE_BY_ZERO|Kayan nokta türü 0.0 ile bölünüyor.|
|STATUS_FLOAT_OVERFLOW|Kayan nokta türünün en fazla pozitif üssü aşılıyor.|
|STATUS_FLOAT_UNDERFLOW|Kayan nokta türünün en düşük negatif üssünün büyüklüğü aşılıyor.|
|STATUS_FLOATING_RESEVERED_OPERAND|Ayrılmış bir kayan nokta biçimi (geçersiz kullanım biçimi) kullanılıyor.|
|STATUS_ILLEGAL_INSTRUCTION|İşlemci tarafından tanımlanmayan bir yönerge kodu yürütülmeye çalışılıyor.|
|STATUS_PRIVILEGED_INSTRUCTION|Geçerli makine modunda izin verilmeyen bir yönerge çalıştırılıyor.|
|STATUS_INTEGER_DIVIDE_BY_ZERO|Bir tamsayı türü 0 ile bölünüyor.|
|STATUS_INTEGER_OVERFLOW|Tamsayının aralığını aşan bir işlem deneniyor.|
|STATUS_SINGLE_STEP|Tek adımlı modda bir yönerge yürütülüyor; yalnızca hata ayıklayıcıları tarafından kullanılır.|

Yukarıdaki tabloda listelenen özel durumların çoğunun hata ayıklayıcılar, işletim sistemi veya başka bir düşük düzeydeki kod tarafından işlenmesi amaçlanır. Tamsayı ve kayan nokta hataları dışında, kodunuzun bu hataları işlememesi gerekir. Bu nedenle, özel durumları yoksaymak (0 olarak değerlendirmek) için genellikle özel durum işleme filtresini kullanmanız gerekir. Aksi takdirde, alt düzey mekanizmaların uygun şekilde yanıt vermesini engelleyebilirsiniz. Ancak, bu düşük düzeydeki hataların olası etkisine karşı uygun önlemler uygulayabileceğiniz [sonlandırma işleyicileri yazarak](../cpp/writing-a-termination-handler.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)