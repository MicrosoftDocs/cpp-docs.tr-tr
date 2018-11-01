---
title: Depolama Sınıfı
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
ms.openlocfilehash: 98e685556fe5dc874f2af818d8c86d0dcadefe29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575675"
---
# <a name="storage-class"></a>Depolama Sınıfı

Bir işlev tanımında depolama sınıfı tanımlayıcısı işlev verir `extern` veya **statik** depolama sınıfı.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> *öznitelik-seq*<sub>iyileştirilmiş</sub> *bildirimci* *bildirim listesi*  <sub>iyileştirilmiş</sub> *bileşik deyim*

/\* *öznitelik-seq* Microsoft Specific \*/

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*depolama sınıfı tanımlayıcısı*: /\* işlev tanımları \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Statik**

Bir işlev tanımı içermiyorsa bir *depolama sınıfı tanımlayıcısı*, depolama sınıfı varsayılan olarak `extern`. Bir işlevi açıkça `extern` olarak bildirebilirsiniz, ancak bu gerekli değildir.

Bir işlevin bildirimi içeriyorsa *depolama sınıfı tanımlayıcısı* `extern`, tanımlayıcı tanımlayıcı dosya konumuna sahip tanımlayıcının görünür bildirimiyle aynı bağlantıya sahiptir. Dosya kapsamına sahip görünür bir bildirim yoksa, tanımlayıcının dış bağlantısı vardır. Tanımlayıcının dosya kapsamı ve Hayır varsa *depolama sınıfı tanımlayıcısı*, tanımlayıcının dış bağlantısı vardır. Dış bağlantı, tanımlayıcının her örneğinin aynı nesneyi veya işlevi gösterdiği anlamına gelir. Bkz: [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) bağlantı ve dosya kapsamı hakkında daha fazla bilgi.

`extern` dışında depolama sınıfı tanımlayıcısına sahip blok kapsamı işlev bildirimleri hata oluşturur.

Bir işlev ile **statik** depolama sınıfı içinde tanımlanmış olduğu yalnızca kaynak dosyasında görülebilir. Diğer tüm işlevler, ister açıkça ister örtük olarak `extern` depolama sınıfı verilsin, programdaki tüm kaynak dosyalarında görülür. Varsa **statik** depolama sınıfı isteniyorsa, bu işlevin bildiriminin (varsa) ilk örneğinde ve işlevin tanımı bildirilmesi gerekir.

**Microsoft'a özgü**

Microsoft uzantıları etkinleştirildiğinde, bir işlevi olarak bildirilen bir depolama sınıfı olmadan (veya `extern` depolama sınıfı) verilen **statik** işlev tanımı aynı kaynak dosyada varsa ve depolama sınıfı tanım açıkça belirten **statik** depolama sınıfı.

/Ze derleyici seçeneğiyle derleme yapılırken, `extern` anahtar sözcüğü kullanılarak bir blok içerisinde bildirilen işlevlerin genel görünürlüğü olur. Bu, /Za ile derleme yapılırken doğru değildir. Kaynak kodunun taşınabilirliği önemliyse, bu özelliğe bağlı kalınmamalıdır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)