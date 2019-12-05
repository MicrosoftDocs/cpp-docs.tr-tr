---
title: C İşlev Tanımları
ms.date: 11/04/2016
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
ms.openlocfilehash: 5cf56375df417ac68b3e03d00f2bd7770ee571e8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857144"
---
# <a name="c-function-definitions"></a>C İşlev Tanımları

İşlev tanımı, işlevin adını, almayı beklediği parametrelerin türlerini ve sayısını ve dönüş türünü belirtir. Bir işlev tanımı Ayrıca yerel değişkenlerinin bildirimlerine sahip bir işlev gövdesini ve işlevin ne yaptığını belirleyecek deyimleri de içerir.

## <a name="syntax"></a>Sözdizimi

*çeviri birimi*:<br/>
&nbsp;&nbsp;&nbsp;*dış bildirimi* &nbsp; <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çeviri-birim* *dış bildirimi*

*Dış bildirim*:/\* yalnızca dış (dosya) kapsam \*izin verildi /<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işlev tanımı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *Bileþik-deyimin*

/\* *özniteliği-seq* , Microsoft 'a özgü \*/

Prototip parametreleri şunlardır:

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub>

*bildirim-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-List* *bildirimi*

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*Direct-bildirimci*:/\* bir işlev bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre türü listesi* **)**  / \* yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**  / \* Kullanımdan kalktı stili bildirimci \*/

Bir tanımdaki parametre listesi bu söz dizimini kullanır:

*parametre-tür-listesi*:/\* parametre listesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* **,...**

*parametre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,** *parametre bildirimi*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *abstract-declarator*<sub>opt</sub>

Eski stil işlev tanımındaki parametre listesi bu söz dizimini kullanır:

*tanımlayıcı listesi*:/\* eski stil işlev tanımlarında ve bildirimlerde kullanılan \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı listesi* **,** *tanımlayıcısı*

İşlev gövdesi için sözdizimi şöyledir:

*bileşik ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *declaration-List*<sub>opt</sub> *bildirimini-List*<sub>opt</sub> **}**

Bir işlev bildirimini değiştirebilen tek depolama sınıfı belirticileri **extern** ve **statiktir**. **Extern** Belirleyicisi, işleve diğer dosyalardan başvurulduğunu belirtir; diğer bir deyişle, işlev adı bağlayıcıya aktarılmalıdır. **Statik** belirtici, işleve diğer dosyalardan başvurulmadığını belirtir; diğer bir deyişle, ad bağlayıcı tarafından aktarılmaz. Bir işlev tanımında hiçbir depolama sınıfı görünürse, **extern** varsayılır. Herhangi bir durumda, işlev her zaman tanım noktasından dosyanın sonuna kadar görünür olur.

İsteğe bağlı *Bildirim belirticileri* ve zorunlu *Bildirimciler* birlikte işlevin dönüş türünü ve adını belirtir. *Bildirimci* , işlev adından sonra işlevi ve ayraçları isimeden tanımlayıcının bir birleşimidir. İsteğe bağlı *öznitelik-Seq* & gt, [işlev özniteliklerinde](../c-language/function-attributes.md)tanımlanmış, Microsoft 'a özgü bir özelliktir.

*Doğrudan bildirimci* ( *bildirimci* sözdiziminde), tanımlanmakta olan işlevin adını ve parametrelerinin tanımlayıcılarını belirtir. *Doğrudan bildirimci* bir *parametre türü listesi*içeriyorsa, liste tüm parametrelerin türlerini belirtir. Bu tür bir bildirimci, daha sonra işlevine çağrılar için bir işlev prototipi işlevi görür.

İşlev tanımlarındaki *bildirim listesindeki* bir *bildirimde* , **yazmaç**dışında bir *depolama sınıfı belirticisi* bulunamaz. *Bildirim tanımlayıcıları* sözdiziminde *tür belirleyicisi* , yalnızca bir **int** türü değeri için **yazmaç** depolama sınıfı belirtilmişse atlanabilir.

*Bileşik deyim* , yerel değişken bildirimlerini, dışarıdan tanımlanmış öğelere başvuruları ve deyimleri içeren işlev gövdesidir.

Bölümler [Işlev öznitelikleri](../c-language/function-attributes.md), [depolama sınıfı](../c-language/storage-class.md), [dönüş türü](../c-language/return-type.md), [Parametreler](../c-language/parameters.md)ve [işlev gövdesi](../c-language/function-body.md) , işlev tanımının bileşenlerini ayrıntılı olarak anlatmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
