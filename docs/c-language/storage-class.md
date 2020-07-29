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
ms.openlocfilehash: 872a014dfc7c21b46f9af810f1cb3463016c7e09
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211690"
---
# <a name="storage-class"></a>Depolama Sınıfı

Bir işlev tanımındaki depolama sınıfı Belirleyicisi, işleve **`extern`** veya **`static`** depolama sınıfına sahip olabilir.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *bileşik-deyimin*

/\**öznitelik-Seq* , Microsoft 'a özgüdür\*/

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub>

*depolama sınıfı-tanımlayıcı*:/ \* işlev tanımları için\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`extern`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`static`**

Bir işlev tanımı bir *depolama sınıfı belirticisi*içermiyorsa, depolama sınıfı varsayılan olarak olur **`extern`** . Bir işlevi açıkça bildirebilirsiniz **`extern`** , ancak gerekli değildir.

Bir işlevin bildirimi *depolama sınıfı belirticisini* içeriyorsa **`extern`** , tanımlayıcı dosya kapsamına sahip olan tanımlayıcının görünür bildirimiyle aynı bağlantıya sahiptir. Dosya kapsamına sahip görünür bir bildirim yoksa, tanımlayıcının dış bağlantısı vardır. Bir tanımlayıcının dosya kapsamı varsa ve *depolama sınıfı Belirleyicisi*yoksa, tanımlayıcının dış bağlantısı vardır. Dış bağlantı, tanımlayıcının her örneğinin aynı nesneyi veya işlevi gösterdiği anlamına gelir. Bağlama ve dosya kapsamı hakkında daha fazla bilgi için bkz. [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) .

Blok kapsamı işlev bildirimleri, hata oluştur dışında bir depolama sınıfı belirticisine sahiptir **`extern`** .

Depolama sınıfına sahip bir işlev **`static`** yalnızca tanımlandığı kaynak dosyada görünür. Tüm diğer işlevler, bir **`extern`** depolama sınıfı açıkça veya örtük olarak verilmiş olsun, programdaki tüm kaynak dosyaları boyunca görünür. **`static`** Depolama sınıfı isteniyorsa, işlevin (varsa) bir bildiriminin ilk oluşumunda ve işlevin tanımında bildirilmesi gerekir.

**Microsoft'a Özgü**

Microsoft uzantıları etkinleştirildiğinde, bir depolama sınıfı olmadan (veya depolama sınıfı ile) ilk olarak bildirildiği bir işleve, **`extern`** **`static`** işlev tanımı aynı kaynak dosyasında yer alıyorsa ve tanım açıkça depolama sınıfını belirtiyorsa, depolama sınıfı verilir **`static`** .

/Ze derleyici seçeneği ile derlerken, anahtar sözcüğünü kullanarak bir blok içinde belirtilen işlevler **`extern`** genel görünürlüğe sahiptir. Bu, /Za ile derleme yapılırken doğru değildir. Kaynak kodunun taşınabilirliği önemliyse, bu özelliğe bağlı kalınmamalıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)
