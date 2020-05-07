---
title: Bildirimlere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, about declarations
- type qualifiers
ms.assetid: fcd2364c-c2a5-4fbf-9027-19dac4144cb5
ms.openlocfilehash: 0ffda6522e632533b0aaa4ba146e8fad082ed435
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857066"
---
# <a name="overview-of-declarations"></a>Bildirimlere Genel Bakış

Bir "bildirim", bir dizi tanımlayıcı için yorumu ve öznitelikleri belirtir. Ayrıca, tanımlayıcı tarafından adlandırılan nesne veya işlev için depolamaya ayrılan bir bildirim, "Tanım" olarak adlandırılır. Değişkenler, işlevler ve türler için C bildirimlerinin bu söz dizimi vardır:

## <a name="syntax"></a>Sözdizimi

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-tanımlayıcılar* *özniteliği-seq*<sub>opt</sub> *init-declarator-list*<sub>opt</sub>**;**

/\**öznitelik-Seq*<sub>opt</sub> , Microsoft 'a özgü */

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *başlatıcısı*

> [!NOTE]
> *Bildirim* için bu sözdizimi aşağıdaki bölümlerde yinelenmez. Aşağıdaki bölümlerde sözdizimi genellikle *bildirimci* olmayan terminalle başlar.

*İnit-declarator-list* içindeki bildirimler, adlandırılmakta olan tanımlayıcıları içerir; *init* başlatıcı için bir kısaltmadır. *İnit-declarator listesi* , her birinin ek tür bilgilerine veya bir başlatıcıya ya da her ikisine de sahip olabilen, virgülle ayrılmış bildirimcilerin bir sırasıdır. *Bildirimci* , varsa, varsa tanımlayıcıları içerir. *Bildirim belirticileri* olmayan Terminal, bağlantı, depolama süresi ve bildirimcilerin işaret eden varlıkların türünün en az bir kısmını belirten bir dizi tür ve depolama sınıfı belirticisinden oluşur. Bu nedenle, bildirimler depolama sınıfı belirticileri, tür belirticileri, tür niteleyicileri, bildirimcilerin ve başlatıcıların bir bileşiminden oluşur.

Bildirimler, *öznitelik-Seq*içinde listelenen bir veya daha fazla isteğe bağlı özniteliği içerebilir. *Seq* , Sequence için bir kısaltmadır. Bu Microsoft 'a özgü öznitelikler, bu kitapta ayrıntılı olarak açıklanan çeşitli işlevler gerçekleştirir.

Bir değişken bildiriminin genel biçiminde *tür belirleyicisi* , değişkenin veri türüne sahip. Tür *belirleyicisi* , türün **const** veya `volatile`tarafından değiştirildiği gibi bir bileşik olabilir. , `declarator` Büyük olasılıkla bir diziyi veya bir işaretçi türünü bildirmek için değiştirilen değişkenin adını verir. Örneğin,

```C
int const *fp;
```

değiştirilemeyen (**const** `int` ) `fp` bir değere işaretçi olarak adlandırılan bir değişken bildirir. Bir bildirimde birden fazla değişkeni virgülle ayırarak birden fazla bildirimci kullanarak tanımlayabilirsiniz.

Bir bildirimde en az bir bildirimci olmalıdır ya da tür belirleyicisi bir yapı etiketi, birleşim etiketi veya bir numaralandırmanın üyelerini bildirmelidir. Bildirimciler, bir tanımlayıcı hakkında kalan bilgileri sağlar. Bildirimci, sırasıyla bir dizi, işaretçi veya işlev türü bildirmek için köşeli ayraç (**[]**)<strong>\*</strong>, yıldız işareti () veya parantez ( **()** ) ile değiştirilebilen bir tanıtıcıdır. Basit değişkenler (karakter, tamsayı ve kayan nokta öğeleri gibi) ya da basit değişkenlerin `declarator` yapıları ve birleşimleri bildirdiğinizde, yalnızca bir tanımlayıcıdır. Bildirimciler hakkında daha fazla bilgi için bkz. [bildiriciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md).

Tüm tanımlar örtük bildirimlerdir, ancak tüm bildirimler tanımlardır. Örneğin, `extern` depolama sınıfı belirticisiyle başlayan değişken bildirimleri "tanımlama" bildirimleri yerine "başvurmalıdır". Bir dış değişken tanımlanmadan önce, veya kullanıldığı bilgisayardan başka bir kaynak dosyasında tanımlanmışsa, bir `extern` bildirim gereklidir. Depolama "başvuru" bildirimleri ile ayrılmaz ve bildirimlerde değişkenler başlatılabilir.

Değişken bildirimlerinde bir depolama sınıfı veya bir tür (veya her ikisi de) gereklidir. Dışında `__declspec`, bildiriminde yalnızca bir depolama sınıfı belirticisine izin verilir ve her bağlamda tüm depolama sınıfı belirticilerine izin verilmez. `__declspec` Depolama sınıfına diğer depolama sınıfı belirticileriyle izin verilir ve birden çok kez kullanılabilir. Bir bildirimin depolama sınıfı Belirleyicisi, belirtilen öğenin nasıl depolandığını ve başlatıldığını ve bir programın hangi bölümlerinin öğeye başvurabileceğini etkiler.

C 'de tanımlanan *depolama sınıfı Belirleyicisi* terminallerinin **Auto**, `extern`, **yazmaç**, **static**ve `typedef`içerir. Ayrıca, Microsoft C, *depolama sınıfı tanımlayıcısı* terminalini `__declspec`içerir. `typedef` Ve `__declspec` dışındaki tüm *depolama sınıfı Belirleyicisi* terminallerini [depolama sınıflarında](../c-language/c-storage-classes.md)ele alınmıştır. Hakkında `typedef`bilgi için bkz. [typedef bildirimleri](../c-language/typedef-declarations.md) . Hakkında `__declspec`bilgi için bkz. [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md) .

Kaynak programdaki bildirimin konumu ve değişkenin diğer bildirimlerinin varlığı veya yokluğu, değişkenlerin ömrünü belirlemede önemli faktörlerdir. Birden çok yeniden bildirim olabilir ancak yalnızca bir tanım olabilir. Ancak, bir tanım birden fazla çeviri biriminde görünebilir. İç bağlantıya sahip nesneler için, dahili bağlantılı nesneler bir çeviri birimine benzersiz olduğundan, bu kural her bir çeviri birimine ayrı olarak uygulanır. Dış bağlantısına sahip nesneler için bu kural tüm programa uygulanır. Görünürlük hakkında daha fazla bilgi için bkz. [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) .

Tür belirticileri, tanımlayıcıların veri türleri hakkında bazı bilgiler sağlar. Varsayılan tür belirleyicisi `int`. Daha fazla bilgi için bkz. [tür tanımlayıcıları](../c-language/c-type-specifiers.md). Tür belirticileri ayrıca tür etiketlerini, yapıyı ve birleşim bileşen adlarını ve numaralandırma sabitlerini de tanımlayabilir. Daha fazla bilgi için bkz. [numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md), [Yapı bildirimleri](../c-language/structure-declarations.md)ve [birleşim bildirimleri](../c-language/union-declarations.md).

İki *tür niteleyicisi* terminalleri vardır: **const** ve `volatile`. Bu niteleyiciler, yalnızca o türdeki nesnelere l-Values aracılığıyla erişirken alakalı olan türlerin ek özelliklerini belirler. **Const** ve `volatile`hakkında daha fazla bilgi Için bkz. [Tür niteleyicileri](../c-language/type-qualifiers.md). L değerlerinin tanımı için bkz. [l-Value ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md).

## <a name="see-also"></a>Ayrıca bkz.

[C Dili Sözdizimi Özeti](../c-language/c-language-syntax-summary.md)<br/>
[Bildirimler ve türler](../c-language/declarations-and-types.md)<br/>
[Bildirimlerin Özeti](../c-language/summary-of-declarations.md)
