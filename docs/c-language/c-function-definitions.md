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
ms.openlocfilehash: 61662caf28fad2f961a580cf280799711a6909bb
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147691"
---
# <a name="c-function-definitions"></a>C İşlev Tanımları

Bir işlev tanımı işlev türlerini ve sayısını almak için bekliyor parametreler ve dönüş türü adını belirtir. Bir işlev tanımı bir işlev gövdesinin bildirimli kendi yerel değişkenlerin ve işlevin ne yaptığını belirlemek için ifadeleri de içerir.

## <a name="syntax"></a>Sözdizimi

*Çeviri birimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Dış bildirimi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Çeviri birimi* *dış bildirimi*

*Dış bildirimi*: /\* yalnızca dış (dosyası) kapsamında izin \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işlev tanımı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> *öznitelik-seq*<sub>iyileştirilmiş</sub> *bildirimci* *bildirim listesi*  <sub>iyileştirilmiş</sub> *bileşik deyim*

/\* *öznitelik-seq* Microsoft Specific \*/

Prototip Parametreler şunlardır:

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*bildirim listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim listesi* *bildirimi*

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*: /\* işlev bildirimcisi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre türü listesi* **)**  / \* yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**  / \* Kullanımdan kalktı stili bildirimci \*/

Bir tanım parametre listesinde bu söz dizimini kullanır:

*parametre türü listesi*: /\* parametre listesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,...**

*parametre listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,** *parametre bildirimi*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *bildirimcisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *soyut bildirimci*<sub>iyileştirilmiş</sub>

Eski stil işlev tanımı parametre listesinde bu söz dizimini kullanır:

*tanımlayıcı listesi*: /\* eski stil işlev tanımları ve bildirimleri \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı listesi* **,** *tanımlayıcısı*

İşlev gövdesi için sözdizimi aşağıdaki gibidir:

*Bileşik deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *bildirim listesi*<sub>iyileştirilmiş</sub> *deyim listesindeki*<sub>iyileştirilmiş</sub> **}**

Bir işlev bildirimi değiştirebileceğiniz yalnızca depolama sınıfı tanımlayıcıları **extern** ve **statik**. **Extern** belirticisi işlev diğer dosyalardan başvurulabilir gösterir; diğer bir deyişle, işlev adını bağlayıcıya dışarı aktarılır. **Statik** belirticisi işlev diğer dosyalardan başvurulamaz gösterir; diğer bir deyişle, ad bağlayıcı tarafından verilebilir. Hiçbir depolama sınıfı bir işlev tanımında görünürse **extern** varsayılır. Herhangi bir durumda, işlev her zaman tanımı noktasından dosyasının sonuna görülebilir.

İsteğe bağlı *bildirim tanımlayıcıları* ve zorunlu *bildirimci* birlikte işlevin dönüş türü ve adı belirtin. *Bildirimci* adları işlevi ve işlev adının parantez tanımlayıcı bir birleşimidir. İsteğe bağlı *öznitelik-seq* Microsoft'a özgü Terminal dışı tanımlanan özellik [işlev öznitelikleri](../c-language/function-attributes.md).

*Doğrudan bildirimci* (içinde *bildirimci* sözdizimi) tanımlanan işlevin adını ve parametrelerini tanımlayıcısını belirtir. Varsa *doğrudan bildirimci* içeren bir *parametre türü listesi*, tüm parametrelerinin türleri listesini belirtir. Böyle bir bildirimcide bir işlev prototipi işleve yapılan sonraki çağrılar için de görür.

A *bildirimi* içinde *bildirim listesi* işlev tanımları içeremez bir *depolama sınıfı tanımlayıcısı* dışında **kaydetme**. *Tür tanımlayıcısı* içinde *bildirim tanımlayıcıları* yalnızca söz dizimi atlanabilir **kaydetme** depolama sınıfı için bir değer belirtilirse **int** türü.

*Compound-statement* olan yerel değişken bildirimleri, başvuruları harici olarak bildirilen öğeler ve deyimleri içeren işlev gövdesi.

Aşağıdaki bölümlerde [işlev öznitelikleri](../c-language/function-attributes.md), [depolama sınıfı](../c-language/storage-class.md), [dönüş türü](../c-language/return-type.md), [parametreleri](../c-language/parameters.md), ve [işlevgövdesi](../c-language/function-body.md) ayrıntılı işlev tanımının bileşenlerini açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
