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
ms.openlocfilehash: aa6e977b3aa03b5f08901cfa8b0abe1b4046e72d
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857014"
---
# <a name="storage-class"></a>Depolama Sınıfı

Bir işlev tanımındaki depolama sınıfı Belirleyicisi, işleve veya **statik** depolama sınıfına sahip `extern` olabilir.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *bileşik-deyimin*

/\**öznitelik-Seq* , Microsoft 'a özgüdür\*/

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub>

*depolama sınıfı-tanımlayıcı*:/\* işlev tanımları için\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Dış**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**se**

Bir işlev tanımı bir *depolama sınıfı belirticisi*içermiyorsa, depolama sınıfı varsayılan olarak `extern`olur. Bir işlevi açıkça `extern` olarak bildirebilirsiniz, ancak bu gerekli değildir.

Bir işlevin bildirimi *depolama sınıfı belirticisini* `extern`içeriyorsa, tanımlayıcı dosya kapsamına sahip olan tanımlayıcının görünür bildirimiyle aynı bağlantıya sahiptir. Dosya kapsamına sahip görünür bir bildirim yoksa, tanımlayıcının dış bağlantısı vardır. Bir tanımlayıcının dosya kapsamı varsa ve *depolama sınıfı Belirleyicisi*yoksa, tanımlayıcının dış bağlantısı vardır. Dış bağlantı, tanımlayıcının her örneğinin aynı nesneyi veya işlevi gösterdiği anlamına gelir. Bağlama ve dosya kapsamı hakkında daha fazla bilgi için bkz. [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) .

`extern` dışında depolama sınıfı tanımlayıcısına sahip blok kapsamı işlev bildirimleri hata oluşturur.

**Statik** depolama sınıfına sahip bir işlev yalnızca tanımlandığı kaynak dosyada görünür. Diğer tüm işlevler, ister açıkça ister örtük olarak `extern` depolama sınıfı verilsin, programdaki tüm kaynak dosyalarında görülür. **Statik** depolama sınıfı isteniyorsa, işlevin (varsa) bir bildiriminin ilk oluşumunda ve işlevin tanımında bildirilmesi gerekir.

**Microsoft'a Özgü**

Microsoft uzantıları etkinleştirildiğinde, bir depolama sınıfı olmadan (veya depolama sınıfı ile `extern` ) ilk olarak bildirildiği bir işleve, işlev tanımı aynı kaynak dosyasında yer alıyorsa ve tanım açıkça **statik** depolama sınıfını belirtiyorsa **statik** depolama sınıfı verilir.

/Ze derleyici seçeneğiyle derleme yapılırken, `extern` anahtar sözcüğü kullanılarak bir blok içerisinde bildirilen işlevlerin genel görünürlüğü olur. Bu, /Za ile derleme yapılırken doğru değildir. Kaynak kodunun taşınabilirliği önemliyse, bu özelliğe bağlı kalınmamalıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
