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
ms.openlocfilehash: 4f793e8485628faf0a80445ce0414835e3b71d1f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217174"
---
# <a name="c-storage-classes"></a>C Depolama Sınıfları

Bir değişkenin "depolama sınıfı", öğenin bir "genel" veya "yerel" yaşam süresine sahip olup olmadığını belirler. C, bu iki yaşam süresi "static" ve "otomatik" çağırır. Genel yaşam süresine sahip bir öğe var ve programın yürütülmesi boyunca bir değere sahip. Tüm işlevlerin küresel yaşam süreleri vardır.

Otomatik değişkenler veya yerel yaşam süreleri olan değişkenler, her yürütme denetimi tanımlandıkları bloğa her geçtiğinde yeni depolama alanı ayrılır. Yürütme döndüğünde, değişkenlerin artık anlamlı değerleri yoktur.

C aşağıdaki depolama sınıfı belirticilerini sağlar:

## <a name="syntax"></a>Sözdizimi

*depolama sınıfı Belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`auto`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`register`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`static`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`extern`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`typedef`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__declspec (`***Extended-decl-değiştirici-seq* **`)`**  / \* Microsoft 'a özgü\*/

Haricinde **`__declspec`** , bildiriminde *bildirim belirticisi* içinde yalnızca bir *depolama sınıfı Belirleyicisi* kullanabilirsiniz. Depolama sınıfı belirtimi yapılbelirtilmemişse, blok içindeki bildirimler otomatik nesneler oluşturur.

**`auto`** Veya belirticisiyle belirtilen öğelerin **`register`** yerel yaşam süreleri vardır. **`static`** Veya belirticisiyle belirtilen öğelerin **`extern`** küresel yaşam süreleri vardır.

**`typedef`** Ve **`__declspec`** diğer dört *depolama sınıfı Belirleyicisi* terminalinden farklı anlam içerdiğinden, bunlar ayrı olarak ele alınmıştır. Hakkında belirli bilgiler için **`typedef`** bkz. [ `typedef` Bildirimler](../c-language/typedef-declarations.md). Hakkında belirli bilgiler için **`__declspec`** bkz. [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

Değişken ve işlev bildirimlerinin kaynak dosyalar içinde yerleştirilmesi, depolama sınıfını ve görünürlüğünü de etkiler. Tüm işlev tanımlarının dışındaki bildirimler "dış düzeyde" gözükme söylenir. İşlev tanımlarının içindeki bildirimler "iç düzeyde" görünür.

Her depolama sınıfı tanımlayıcısının tam anlamı iki etkene bağlıdır:

- Bildirimin dış veya iç düzeyde görünüp görüntülenmediğini belirtir

- Belirtilen öğenin bir değişken veya işlev olup olmadığı

[Dış düzey bildirimlerin](../c-language/storage-class-specifiers-for-external-level-declarations.md) depolama sınıfı belirticileri ve [iç düzey bildirimlerin](../c-language/storage-class-specifiers-for-internal-level-declarations.md) depolama sınıfı belirticileri, her bir bildirimde bulunan *depolama sınıfı Belirleyicisi* terminallerini açıklar ve *depolama sınıfı Belirleyicisi* bir değişkenden atlandığında varsayılan davranışı açıklar. [Işlev bildirimleriyle depolama sınıfı belirticileri,](../c-language/storage-class-specifiers-with-function-declarations.md) işlevlerle kullanılan depolama sınıfı belirticilerini tartışır.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
