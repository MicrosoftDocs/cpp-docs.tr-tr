---
description: 'Hakkında daha fazla bilgi edinin: bildirimlere genel bakış'
title: Bildirimlere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, about declarations
- type qualifiers
ms.assetid: fcd2364c-c2a5-4fbf-9027-19dac4144cb5
ms.openlocfilehash: 53b8c808771aa3bb455655e6e0c5b06ff1fa9acd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256854"
---
# <a name="overview-of-declarations"></a>Bildirimlere Genel Bakış

Bir "bildirim", bir dizi tanımlayıcı için yorumu ve öznitelikleri belirtir. Ayrıca, tanımlayıcı tarafından adlandırılan nesne veya işlev için depolamaya ayrılan bir bildirim, "Tanım" olarak adlandırılır. Değişkenler, işlevler ve türler için C bildirimlerinin bu söz dizimi vardır:

## <a name="syntax"></a>Syntax

*`declaration`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declaration-specifiers`**`attribute-seq`* <sub>opt</sub> *`init-declarator-list`* <sub>kabul</sub>**`;`**

/\**`attribute-seq`* <sub>opt</sub> Microsoft 'a özgü */

*`declaration-specifiers`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`storage-class-specifier`**`declaration-specifiers`* <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`type-specifier`**`declaration-specifiers`* <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`type-qualifier`**`declaration-specifiers`* <sub>opt</sub>

*`init-declarator-list`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`init-declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`init-declarator-list`* **`,`** *`init-declarator`*

*`init-declarator`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declarator`* **`=`** *`initializer`*

> [!NOTE]
> İçin bu söz dizimi *`declaration`* Aşağıdaki bölümlerde yinelenmez. Aşağıdaki bölümlerde sözdizimi genellikle *`declarator`* terminalle başlar.

İçindeki bildirimler, olarak *`init-declarator-list`* adlandırılmakta olan tanımlayıcıları içerir; *`init`* Başlatıcı için bir kısaltmadır. , *`init-declarator-list`* Her birinin ek tür bilgilerine veya bir başlatıcıya ya da her ikisine de sahip olabilen, virgülle ayrılmış bildirimcilerin bir sırasıdır. , *`declarator`* Varsa, tanımlayıcıları içerir. *`declaration-specifiers`*& Gt, bağlantı, depolama süresi ve bildirimcilerin işaret eden varlıkların türünün en az bir kısmını belirten bir dizi tür ve depolama sınıfı belirticisinden oluşur. Bildirimler, bazı depolama sınıfı belirticileri, tür belirticileri, tür niteleyicileri, bildirimcilerin ve başlatıcıların birleşiminden oluşur.

Bildirimler, içinde listelenen bir veya daha fazla isteğe bağlı özniteliği içerebilir *`attribute-seq`* ; *`seq`* dizi için bir kısaltmadır. Bu Microsoft 'a özgü öznitelikler, bu kitapta ayrıntılı olarak açıklanan birkaç işlevi gerçekleştirir.

Bir değişken bildiriminin genel biçiminde, *`type-specifier`* değişkenin veri türünü verir. , *`type-specifier`* Türü veya tarafından değiştirildiği gibi bir bileşik olabilir **`const`** **`volatile`** . , `declarator` Büyük olasılıkla bir diziyi veya bir işaretçi türünü bildirmek için değiştirilen değişkenin adını verir. Örneğin,

```C
int const *fp;
```

`fp`değiştirilemeyen () bir değere işaretçi olarak adlandırılan bir değişken bildirir **`const`** **`int`** . Bir bildirimde birden fazla değişkeni virgülle ayırarak birden fazla bildirimci kullanarak tanımlayabilirsiniz.

Bir bildirimde en az bir bildirimci olmalıdır ya da tür belirleyicisi bir yapı etiketi, birleşim etiketi veya bir numaralandırmanın üyelerini bildirmelidir. Bildirimciler, bir tanımlayıcı hakkında kalan bilgileri sağlar. Bildirimci, **`[ ]`** <strong>`*`</strong> **`( )`** sırasıyla bir dizi, işaretçi veya işlev türü bildirmek için köşeli ayraç (), yıldız işareti () veya parantez () ile değiştirilebilen bir tanıtıcıdır. Basit değişkenler (karakter, tamsayı ve kayan nokta öğeleri gibi) ya da basit değişkenlerin yapıları ve birleşimleri bildirdiğinizde, `declarator` yalnızca bir tanımlayıcıdır. Bildirimciler hakkında daha fazla bilgi için bkz. [bildiriciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md).

Tüm tanımlar örtük bildirimlerdir, ancak tüm bildirimler tanımlardır. Örneğin, **`extern`** depolama sınıfı belirticisiyle başlayan değişken bildirimleri "tanımlama" bildirimleri yerine "başvurmalıdır". Bir dış değişken tanımlanmadan önce veya bir başka kaynak dosyasında tanımlanmazsa, bir **`extern`** bildirim gerekir, bir bildirim gereklidir. Depolama "başvuru" bildirimleri ile ayrılmaz ve bildirimlerde değişkenler başlatılabilir.

Değişken bildirimlerinde bir depolama sınıfı veya bir tür (veya her ikisi de) gereklidir. Dışında **`__declspec`** , bildiriminde yalnızca bir depolama sınıfı belirticisine izin verilir ve her bağlamda tüm depolama sınıfı belirticilerine izin verilmez. **`__declspec`** Depolama sınıfına diğer depolama sınıfı belirticileriyle izin verilir ve birden çok kez kullanılabilir. Bir bildirimin depolama sınıfı Belirleyicisi, belirtilen öğenin nasıl depolandığını ve başlatıldığını ve bir programın hangi bölümlerinin öğeye başvurabileceğini etkiler.

*`storage-class-specifier`* C 'de tanımlanan Terminaller,, **`auto`** , **`extern`** ve **`register`** içerir **`static`** **`typedef`** . Microsoft C, Terminal de *`storage-class-specifier`* içerir **`__declspec`** . *`storage-class-specifier`* Ve dışındaki tüm terminallerde **`typedef`** **`__declspec`** [depolama sınıflarında](../c-language/c-storage-classes.md)tartışılmıştır. Hakkında bilgi için **`typedef`** bkz. [ `typedef` Bildirimler](../c-language/typedef-declarations.md). Hakkında daha fazla bilgi için **`__declspec`** bkz. [genişletilmiş Storage-Class öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

Kaynak programdaki bildirimin konumu ve değişkenin diğer bildirimlerinin varlığı veya yokluğu, değişkenlerin ömrünü belirlemede önemli faktörlerdir. Birden çok yeniden bildirim olabilir ancak yalnızca bir tanım olabilir. Ancak, bir tanım birden fazla çeviri biriminde görünebilir. İç bağlantıya sahip nesneler için, dahili bağlantılı nesneler bir çeviri birimine benzersiz olduğundan, bu kural her bir çeviri birimine ayrı olarak uygulanır. Dış bağlantısına sahip nesneler için bu kural tüm programa uygulanır. Görünürlük hakkında daha fazla bilgi için bkz. [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md).

Tür belirticileri, tanımlayıcıların veri türleri hakkında bazı bilgiler sağlar. Varsayılan tür belirleyicisi **`int`** . Daha fazla bilgi için bkz. [tür tanımlayıcıları](../c-language/c-type-specifiers.md). Tür belirticileri ayrıca tür etiketlerini, yapıyı ve birleşim bileşen adlarını ve numaralandırma sabitlerini de tanımlayabilir. Daha fazla bilgi için bkz. [numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md), [Yapı bildirimleri](../c-language/structure-declarations.md)ve [birleşim bildirimleri](../c-language/union-declarations.md).

İki Terminal vardır *`type-qualifier`* : **`const`** ve **`volatile`** . Bu niteleyiciler, yalnızca o türdeki nesnelere l-Values aracılığıyla erişirken alakalı olan türlerin ek özelliklerini belirler. Ve hakkında daha fazla bilgi için **`const`** **`volatile`** bkz. [Tür niteleyicileri](../c-language/type-qualifiers.md). L değerlerinin tanımı için bkz. [l-Value ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md).

## <a name="see-also"></a>Ayrıca bkz.

[C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md)<br/>
[Bildirimler ve türler](../c-language/declarations-and-types.md)<br/>
[Bildirimlerin Özeti](../c-language/summary-of-declarations.md)
