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
ms.openlocfilehash: 77aefe41fecf003218343710ef090eebf99446a8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857118"
---
# <a name="c-storage-classes"></a>C Depolama Sınıfları

Bir değişkenin "depolama sınıfı", öğenin bir "genel" veya "yerel" yaşam süresine sahip olup olmadığını belirler. C, bu iki yaşam süresi "static" ve "otomatik" çağırır. Genel yaşam süresine sahip bir öğe var ve programın yürütülmesi boyunca bir değere sahip. Tüm işlevlerin küresel yaşam süreleri vardır.

Otomatik değişkenler veya yerel yaşam süreleri olan değişkenler, her yürütme denetimi tanımlandıkları bloğa her geçtiğinde yeni depolama alanı ayrılır. Yürütme döndüğünde, değişkenlerin artık anlamlı değerleri yoktur.

C aşağıdaki depolama sınıfı belirticilerini sağlar:

## <a name="syntax"></a>Sözdizimi

*depolama sınıfı Belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Otomatik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Kaydet**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**statik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**typedef**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *Genişletilmiş-decl-değiştirici-seq* **)**  /\* Microsoft 'a özgü \*/

`__declspec`haricinde, bir bildirimde *bildirim belirticisi* içinde yalnızca bir *depolama sınıfı Belirleyicisi* kullanabilirsiniz. Depolama sınıfı belirtimi yapılbelirtilmemişse, blok içindeki bildirimler otomatik nesneler oluşturur.

**Auto** veya **yazmaç** belirticisi ile belirtilen öğelerin yerel yaşam süreleri vardır. **Statik** veya `extern` belirticisiyle belirtilen öğelerin küresel yaşam süreleri vardır.

`typedef` ve `__declspec` diğer dört *depolama sınıfı Belirleyicisi* terminallerinden farklı olduğundan, bunlar ayrı olarak ele alınmıştır. `typedef`hakkındaki özel bilgiler için bkz. [typedef bildirimleri](../c-language/typedef-declarations.md). `__declspec`hakkında belirli bilgiler için bkz. [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

Değişken ve işlev bildirimlerinin kaynak dosyalar içinde yerleştirilmesi, depolama sınıfını ve görünürlüğünü de etkiler. Tüm işlev tanımlarının dışındaki bildirimler "dış düzeyde" gözükme söylenir. İşlev tanımlarının içindeki bildirimler "iç düzeyde" görünür.

Her depolama sınıfı tanımlayıcısının tam anlamı iki etkene bağlıdır:

- Bildirimin dış veya iç düzeyde görünüp görüntülenmediğini belirtir

- Belirtilen öğenin bir değişken veya işlev olup olmadığı

[Dış düzey bildirimlerin](../c-language/storage-class-specifiers-for-external-level-declarations.md) depolama sınıfı belirticileri ve [iç düzey bildirimlerin](../c-language/storage-class-specifiers-for-internal-level-declarations.md) depolama sınıfı belirticileri, her bir bildirimde bulunan *depolama sınıfı Belirleyicisi* terminallerini açıklar ve *depolama sınıfı Belirleyicisi* bir değişkenden atlandığında varsayılan davranışı açıklar. [Işlev bildirimleriyle depolama sınıfı belirticileri,](../c-language/storage-class-specifiers-with-function-declarations.md) işlevlerle kullanılan depolama sınıfı belirticilerini tartışır.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)
