---
title: Parametreler
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], function
- function parameters
- parameters [C++]
- function arguments, vs. parameters
- parameters [C++], function
- functions [C], parameters
- function parameters, syntax
- ellipsis (...), parameters
- '... ellipsis'
ms.assetid: 8f2b8026-78b5-4e21-86a3-bf0f91f05689
ms.openlocfilehash: 78ad91ea86d81a3b6d888335ba7b78399a1d2aea
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032076"
---
# <a name="parameters"></a>Parametreler

Bağımsız değişkenler bir işleve işlev çağrısı tarafından geçirilen değerlerin adlarıdır. Parametreler, işlevin almayı beklediği değerlerdir. Bir işlev prototipinden, işlev adını izleyen parantezler işlevin parametrelerinin ve türlerinin tamamen bir listesini içerir. Parametre bildirimleri, parametrelerde depolanan değerlerin türlerini, boyutlarını ve tanımlayıcılarını belirler.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *bileşik-deyimin*

/\**öznitelik-Seq* , Microsoft 'a özgüdür\*/

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*Direct-bildirimci*:/\* bir işlev bildirimci\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-bildirimci***(***parametre türü-liste***)**  / \* yeni stil bildirimci      \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-bildirimci***(***tanımlayıcı listesi*<sub>opt</sub> **)**  / \* eski stil bildirimci    \*/

*parametre-tür-listesi*:/\* parametre listesi\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-liste* **,...**

*parametre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* **,**  *parametre bildirimi*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-tanımlayıcılar* *abstract-bildirimci*<sub>opt</sub>

*Parametre türü-listesi* , virgülle ayrılmış bir parametre bildirimleri dizisidir. Bir parametre listesindeki her parametrenin biçimi şöyle görünür:

```C
[register]  type-specifier [declarator]
```

**Auto** özniteliğiyle belirtilen işlev parametreleri hata oluştur. Parametre tanımlayıcıları, işleve geçirilen değerlere başvurmak için işlev gövdesinde kullanılır. Bir prototipde parametreleri isimlendirebilmeniz, ancak adlar bildirimin sonundaki kapsam dışına çıkar. Bu nedenle parametre adları, işlev tanımında aynı şekilde veya farklı şekilde atanabilir. Bu tanımlayıcılar, işlev gövdesinin en dıştaki bloğunda yeniden tanımlanamaz, ancak parametre listesi kapsayan bir blok olmasına rağmen iç, iç içe bloklar içinde yeniden tanımlanabilir.

*Parametre türü listedeki* her tanımlayıcı, bu örnekte gösterildiği gibi, önce uygun tür belirticisinden önce gelmelidir:

```C
void new( double x, double y, double z )
{
    /* Function body here */
}
```

Parametre listesinde en az bir parametre oluşursa, liste bir virgül ile ve ardından üç nokta (**,...**) ile bitebilirler. "Üç nokta gösterimi" olarak adlandırılan bu yapım, işlev için değişken sayıda bağımsız değişken belirtir. (Daha fazla bilgi için bkz. [değişken sayıda bağımsız değişkene sahip çağrılar](../c-language/calls-with-a-variable-number-of-arguments.md) .) Ancak, bir işlev çağrısının en az sayıda bağımsız değişkeni olması gerekir ve bu, son virgülden önce parametre vardır.

İşleve hiçbir bağımsız değişken geçirilmezse, parametrelerin listesi, anahtar sözcüğüyle `void`değiştirilmiştir. Bu kullanımı `void` , bir tür belirleyici olarak kullanımıyla farklıdır.

Üç nokta gösteriminin kullanımı dahil olmak üzere parametrelerin sırası ve türü, tüm işlev bildirimlerinde ve işlev tanımında aynı olmalıdır. Her zamanki aritmetik dönüşümlerden sonraki bağımsız değişkenlerin türleri, karşılık gelen parametrelerin türleriyle atama ile uyumlu olmalıdır. (Aritmetik dönüştürmeler hakkında bilgi için bkz. [normal aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) .) Üç nokta ile sonraki bağımsız değişkenler işaretli değil. Bir parametre herhangi bir temel, yapı, birleşim, işaretçi veya dizi türüne sahip olabilir.

Derleyici, her bir parametrede ve gerekirse her bağımsız değişkende her zaman bağımsız olarak her bir aritmetik dönüştürme gerçekleştirir. Dönüştürmeden sonra, hiçbir parametre bir `int`değerden daha kısadır ve parametre türü açıkça prototipi içinde **float** olarak belirtilmedikçe hiçbir parametre **float** türüne sahip değildir. Bu, örneğin, bir parametresinin bir `char` olarak bildirilmesinin aynı etkiye sahip olduğu anlamına gelir. `int`

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
