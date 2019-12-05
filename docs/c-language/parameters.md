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
- ellipses (...), parameters
- '... ellipsis'
ms.assetid: 8f2b8026-78b5-4e21-86a3-bf0f91f05689
ms.openlocfilehash: f2fd4b49e08149f8ea5ce8fa6af46da39907dcf9
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857053"
---
# <a name="parameters"></a>Parametreler

Bağımsız değişkenler bir işleve işlev çağrısı tarafından geçirilen değerlerin adlarıdır. Parametreler, işlevin almayı beklediği değerlerdir. Bir işlev prototipinden, işlev adını izleyen parantezler işlevin parametrelerinin ve türlerinin tamamen bir listesini içerir. Parametre bildirimleri, parametrelerde depolanan değerlerin türlerini, boyutlarını ve tanımlayıcılarını belirler.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *Bileþik-deyimin*

/\* *özniteliği-seq* , Microsoft 'a özgü \*/

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*Direct-bildirimci*:/\* bir işlev bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre türü listesi* **)**  / \* yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**  / \* Kullanımdan kalktı stili bildirimci \*/

*parametre-tür-listesi*:/\* parametre listesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* **,...**

*parametre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,** *parametre bildirimi*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *abstract-declarator*<sub>opt</sub>

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

Parametre listesinde en az bir parametre oluşursa, liste bir virgül ile ve ardından üç nokta ( **,...** ) ile bitebilirler. "Üç nokta gösterimi" olarak adlandırılan bu yapım, işlev için değişken sayıda bağımsız değişken belirtir. (Daha fazla bilgi için bkz. [değişken sayıda bağımsız değişkene sahip çağrılar](../c-language/calls-with-a-variable-number-of-arguments.md) .) Ancak, bir işlev çağrısının en az sayıda bağımsız değişkeni olması gerekir ve bu, son virgülden önce parametre vardır.

İşleve hiçbir bağımsız değişken geçirilmezse, parametrelerin listesi `void`anahtar kelimesiyle değiştirilmiştir. Bu `void` kullanımı, bir tür tanımlayıcısı olarak kullanımı farklıdır.

Üç nokta gösteriminin kullanımı dahil olmak üzere parametrelerin sırası ve türü, tüm işlev bildirimlerinde ve işlev tanımında aynı olmalıdır. Her zamanki aritmetik dönüşümlerden sonraki bağımsız değişkenlerin türleri, karşılık gelen parametrelerin türleriyle atama ile uyumlu olmalıdır. (Aritmetik dönüştürmeler hakkında bilgi için bkz. [normal aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) .) Üç nokta ile sonraki bağımsız değişkenler işaretli değil. Bir parametre herhangi bir temel, yapı, birleşim, işaretçi veya dizi türüne sahip olabilir.

Derleyici, her bir parametrede ve gerekirse her bağımsız değişkende her zaman bağımsız olarak her bir aritmetik dönüştürme gerçekleştirir. Dönüştürmeden sonra, hiçbir parametre bir `int`daha kısadır ve parametre türü açıkça prototipi içinde **float** olarak belirtilmedikçe hiçbir parametre **float** türüne sahip değildir. Bu, örneğin, bir `char` olarak bir parametre bildiren, `int`olarak bildirme ile aynı etkiye sahip olduğu anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
