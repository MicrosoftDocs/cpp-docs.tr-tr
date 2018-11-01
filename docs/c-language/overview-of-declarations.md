---
title: Bildirimlere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, about declarations
- type qualifiers
ms.assetid: fcd2364c-c2a5-4fbf-9027-19dac4144cb5
ms.openlocfilehash: 4e6c166763afd18db79798024d8b2f159ffed76d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582763"
---
# <a name="overview-of-declarations"></a>Bildirimlere Genel Bakış

Bir "bildirim" yorumunu ve tanımlayıcıları Kümesi özniteliklerini belirtir. Ayrıca nesne veya işlev tanımlayıcısının adlı için ayrılmış depolama neden olan bir bildirim "tanımı." olarak adlandırılır C bildirimleri değişkenler, İşlevler ve türleri için bu sözdizimine sahiptir:

## <a name="syntax"></a>Sözdizimi

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *öznitelik-seq*<sub>iyileştirilmiş</sub> *init-declarator-list*<sub>iyileştirilmiş</sub>**;**

/\* *öznitelik-seq*<sub>iyileştirilmiş</sub> Microsoft özgüdür * /

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *Başlatıcı*

> [!NOTE]
> Bu sözdiziminin *bildirimi* aşağıdaki bölümlerde yinelenmez. Aşağıdaki bölümlerde söz dizimi ile genellikle başlayan *bildirimci* bildirimlere.

Bildirimler *init-declarator-list* adın geçmesi; tanımlayıcılar içeriyor *init* için Başlatıcı ifadesinin kısaltmasıdır. *İnit-declarator-list* virgülle ayrılmış bir Bildirimciler, her biri olabilir ek tür bilgileri, bir başlatıcıya veya her dizi olan. *Bildirimci* varsa bildirilen tanımlayıcılar içeriyor. *Bildirim tanımlayıcıları* bildirimlere gösteren depolama süresi, bağlantı türü ve depolama sınıfı tanımlayıcıları bir dizi oluşur ve en az bir parçası Bildirimciler belirtmek varlık türü. Bu nedenle, bildirimleri depolama sınıfı tanımlayıcıları, tür tanımlayıcıları, tür niteleyicileri, bildirimler ve başlatıcılar bileşiminden oluşur.

Bildirimleri birini içerebilir veya daha fazla isteğe bağlı öznitelik listelenen *öznitelik-seq*; *seq* dizisi kısaltmasıdır. Bu Microsoft özel öznitelikler bu kitap boyunca ayrıntılı ele alınmıştır işlevleri, çeşitli gerçekleştirin.

Bir Değişken bildiriminde genel biçiminde *tür tanımlayıcısı* değişkeninin veri türü sunar. *Tür tanımlayıcısı* türü tarafından değiştirildiğinde olarak bir bileşik olabilir **const** veya `volatile`. `declarator` Büyük olasılıkla bir dizi veya işaretçi türünde bildirmeniz değiştirilmiş değişkeninin adını verir. Örneğin,

```C
int const *fp;
```

adlı bir değişken bildirir `fp` değiştirilemez bir işaretçisi olarak (**const**) `int` değeri. Virgülle ayırarak birden çok bildirimcisi kullanarak bir bildirimde birden fazla değişken tanımlayabilirsiniz.

Bir bildirimi en az bir bildirimci sahip olmalıdır veya kendi tür belirticisi, bir yapı etiketi, birleşim etiketi veya bir sabit listesi üyesi bildirmeniz gerekir. Bildirimciler, kalan herhangi bir tanımlayıcı bilgileri sağlar. Bir bildirimci köşeli parantez ile değiştirilebilir bir tanımlayıcıdır (**[]**), yıldız işareti (<strong>\*</strong>), veya parantezler ( **()** ) bir diziyi bildirmek için işaretçi, veya işlev türü, sırasıyla. (Örneğin, karakter, tamsayı ve kayan nokta öğeleri), basit değişkenler veya yapılar ve birleşimler basit değişken bildirdiğinizde `declarator` yalnızca bir tanımlayıcıdır. Bildirimciler hakkında daha fazla bilgi için bkz. [bildirimler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md).

Tüm tanımları örtük olarak bildirimleri, ancak tüm bildirimleri tanımlar. Örneğin, şununla değişken bildirimlerini `extern` depolama sınıfı tanımlayıcısı "başvuran," yerine "tanımlama" bildirimleri. Dış bir değişken tanımlanmadan başvurulacak ise veya bir nereden kullanıldığı, başka bir kaynak dosyasında tanımlanan bir `extern` bildirimi gereklidir. "Bildirimlerini başvurarak" depolama tahsis ve değişken bildirimlerinde başlatılabilir.

Bir depolama sınıfı veya bir tür (veya her ikisi de) değişken bildirimlerinde gereklidir. Dışında `__declspec`, yalnızca bir depolama sınıfı tanımlayıcısı bir bildirimine izin verilir ve tüm depolama sınıfı tanımlayıcıları her bağlamda izin verilir. `__declspec` Depolama sınıfı ile diğer depolama sınıfı tanımlayıcıları izin verilir ve birden çok kez izin verilir. Bildirilen öğe nasıl depolandığını ve başlatılmış ve bir programın hangi parçalarının öğe başvurabilirsiniz bir bildirimin depolama sınıfı tanımlayıcısı etkiler.

*Depolama sınıfı tanımlayıcısı* C'de tanımlanan terminaller dahil **otomatik**, `extern`, **kaydetme**, **statik**ve `typedef`. Ayrıca, Microsoft C içerir *depolama sınıfı tanımlayıcısı* terminal `__declspec`. Tüm *depolama sınıfı tanımlayıcısı* dışında terminaller `typedef` ve `__declspec` ele alınmıştır [depolama sınıfları](../c-language/c-storage-classes.md). Bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md) hakkında bilgi için `typedef`. Bkz: [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md) hakkında bilgi için `__declspec`.

Kaynak program ve varlığından destek alan içindeki bildirim konumunu veya diğer bildirimleri değişkenin olmaması değişkenlerin ömrünü belirlemede önemli faktörler şunlardır. Birden çok redeclarations ancak yalnızca bir tanımı olabilir. Ancak, bir tanımı birden fazla çeviri biriminde görünür. Dahili olarak bağlantılı nesneler bir çeviri birimi için benzersiz olduğundan iç bağlaması olan nesneler için bu kural her çeviri birimi için ayrı ayrı uygulanır. Dış bağlaması olan nesneler için bu kural için tüm programı uygular. Bkz: [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) görünürlük hakkında daha fazla bilgi.

Tür tanımlayıcıları, tanımlayıcıların veri türleri hakkında bazı bilgiler sağlamalısınız. Varsayılan türü belirleyici `int`. Daha fazla bilgi için [tür tanımlayıcıları](../c-language/c-type-specifiers.md). Tür tanımlayıcıları da türü etiketleri, yapı ve birleşim bileşen adlarına ve numaralandırma sabitlerini tanımlayabilirsiniz. Daha fazla bilgi için [numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md), [yapı bildirimleri](../c-language/structure-declarations.md), ve [birleşim bildirimleri](../c-language/union-declarations.md).

İki *tür niteleyici* terminaller: **const** ve `volatile`. Bu niteleyiciler yalnızca bu tür nesneleri l-değerler erişirken ilgilendiren türlerinin ek özellikleri belirtin. Daha fazla bilgi için **const** ve `volatile`, bkz: [tür niteleyicileri](../c-language/type-qualifiers.md). L-değerler tanımı için bkz [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C Dili Sözdizimi Özeti](../c-language/c-language-syntax-summary.md)<br/>
[Bildirimler ve Türler](../c-language/declarations-and-types.md)<br/>
[Bildirimlerin Özeti](../c-language/summary-of-declarations.md)