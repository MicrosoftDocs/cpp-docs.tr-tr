---
title: C Depolama Sınıfları
ms.date: 08/31/2018
helpviewer_keywords:
- static variables, lifetime
- storage classes
- lifetime, variables
- specifiers, storage class
- storage class specifiers, C storage classes
- storage duration
ms.assetid: 893fb929-f7a9-43dc-a0b3-29cb1ef845c1
ms.openlocfilehash: cb472ea0db67e0fd8d7f2a8e2af4513ffb0fbe1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466189"
---
# <a name="c-storage-classes"></a>C Depolama Sınıfları

Bir değişkenin "depolama class" öğe "Genel" veya "yerel" bir ömre sahip olup olmadığını belirler. C bu iki yaşam süreleri, "statik" ve "Otomatik" çağırır. Genel bir ömre sahip bir öğe var ve programın yürütülmesi boyunca bir değere sahip. Tüm İşlevler, genel kullanım ömürleri vardır.

Otomatik değişkenler veya yerel ömürleriyle değişkenleri her zaman yürütme denetim bloğuna geçer, yeni depolama alanı ayrılır, tanımlandıkları içinde. Yürütme geri döndüğünde, değişkenleri artık anlamlı değerlere sahip.

C, aşağıdaki depolama sınıfı tanımlayıcıları sağlar:

## <a name="syntax"></a>Sözdizimi

*depolama sınıfı tanımlayıcısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Otomatik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Kaydolun**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Statik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**tür tanımı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (** *genişletilmiş-decl-değiştirici-seq* **)**  / \* Microsoft Specific \*/

Dışında `__declspec`, tek kullanabileceğiniz *depolama sınıfı tanımlayıcısı* içinde *bildirim belirticisi* bildirimindeki. Hiçbir depolama sınıfı belirtimi yapılmazsa, bir blok içindeki bildirimleri otomatik nesneleri oluşturma.

Bildirilen öğeler ile **otomatik** veya **kaydetme** belirticisi sahip yerel bir yaşam süresi yok. Bildirilen öğeler ile **statik** veya `extern` belirticisi, genel kullanım ömürleri vardır.

Bu yana `typedef` ve `__declspec` diğer dört anlamsal olarak farklı *depolama sınıfı tanımlayıcısı* terminaller, ayrı olarak ele alınmıştır. Özel bilgileri hatırlamasına için `typedef`, bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md). Özel bilgileri hatırlamasına için `__declspec`, bkz: [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

Kaynak dosyaları değişken ve işlev bildirimlerinde yerleşimini depolama sınıfı ve görünürlük de etkiler. Tüm işlev tanımlarının dışında bildirimleri "dış düzeyde." göründüğü söylenir İşlev tanımları bildirimlerinde "İç düzeyinde." görünür.

Her depolama sınıfı tanımlayıcısı tam anlamı iki etkenlere bağlıdır:

- Bildirimi dış veya iç düzeyinde görünüp görünmeyeceğini belirtir

- Bildirilen öğe bir değişken veya işlev olup

[Dış düzey bildirimleri depolama sınıfı tanımlayıcıları](../c-language/storage-class-specifiers-for-external-level-declarations.md) ve [iç düzey bildirimleri depolama sınıfı tanımlayıcıları](../c-language/storage-class-specifiers-for-internal-level-declarations.md) açıklayan *depolama sınıfı tanımlayıcısı* terminaller her tür bir bildirim ve varsayılan davranışı açıklamak olduğunda *depolama sınıfı tanımlayıcısı* bir değişkeninden atlanırsa. [İşlev bildirimli depolama sınıfı tanımlayıcıları](../c-language/storage-class-specifiers-with-function-declarations.md) işlevleri ile kullanılan depolama sınıfı tanımlayıcıları açıklar.

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)
