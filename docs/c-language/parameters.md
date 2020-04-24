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

Bağımsız değişkenler, işlev çağrısıyla işleve aktarılan değerlerin adlarıdır. Parametreler, işlevin almayı beklediği değerlerdir. Bir işlev prototipinde, işlev adını izleyen parantezler işlevin parametrelerinin ve türlerinin tam listesini içerir. Parametre bildirimleri parametrelerde depolanan değerlerin türlerini, boyutlarını ve tanımlayıcılarını belirtir.

## <a name="syntax"></a>Sözdizimi

*fonksiyon tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*beyanname-belirteçler* *öznitelik-seq*<sub>opt</sub> *declarator* *bildirim-liste*opt bileşik *deyimi* <sub>tercih</sub> <sub>opt</sub>

/\**öznitelik-seq* Microsoft'a özgüdür\*/

*beyaneden*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi* *doğrudan bildireni* <sub>tercih eder</sub>

*direct-declarator*:\* / Bir fonksiyon bildiren\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildiren***(***parametre türü-liste***)**  / \* Yeni stil beyanatörü      \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan beyan edici***(***tanımlayıcı-liste*<sub>opt</sub> **)**  / \* Eski tarzda bildirimci    \*/

*parametre türü listesi*:\* / Parametre listesi\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **, ...**

*parametre listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-deklarasyonu*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,**  *parametre-deklarasyon*

*parametre-beyan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*beyan-belirtici* *beyanatörü*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*beyanname-belirtici* *özet-beyanator*<sub>opt</sub>

*Parametre türü listesi,* virgüllerle ayrılmış parametre bildirimleri dizisidir. Parametre listesindeki her parametrenin biçimi aşağıdaki gibi görünür:

```C
[register]  type-specifier [declarator]
```

**Otomatik** öznitelik ile bildirilen işlev parametreleri hatalar oluşturur. Parametrelerin tanımlayıcıları işlev gövdesinde, işleve aktarılan değerlere başvurmak için kullanılır. Parametreleri bir prototipte adlandırabilirsiniz, ancak adlar bildirimin sonunda kapsam dışına çıkar. Bu nedenle parametre adları işlev tanımında aynı şekilde veya farklı olarak atanabilir. Bu tanımlayıcılar işlev gövdesinin en dış bloğunda yeniden tanımlanamaz, ancak parametre listesi çevreleyen bir blokmuş gibi iç, iç içe doğru bloklarda yeniden tanımlanabilir.

*Parametre türü listesindeki* her tanımlayıcı, bu örnekte gösterildiği gibi, uygun tür belirticisinden önce olmalıdır:

```C
void new( double x, double y, double z )
{
    /* Function body here */
}
```

Parametre listesinde en az bir parametre oluşursa, liste virgülle son bulabilir ve ardından üç dönem **(, ...**). "Elipsis gösterimi" olarak adlandırılan bu yapı, işleve değişken sayıda bağımsız değişken gösterir. (Daha fazla bilgi için [Değişken Değişken Sayısına Sahip Çağrılara](../c-language/calls-with-a-variable-number-of-arguments.md) Bakın.) Ancak, işlev çağrısı nın son virgülden önce parametreler olduğu kadar en az sayıda bağımsız değişkeni olmalıdır.

İşleviçin bağımsız değişken geçirilmezse, parametrelerin listesi anahtar sözcük `void`ile değiştirilir. Bu `void` kullanım, bir tür belirtici olarak kullanımıfarklıdır.

Elipsgösterimin herhangi bir kullanımı da dahil olmak üzere parametrelerin sırası ve türü, tüm işlev bildirimlerinde (varsa) ve işlev tanımında aynı olmalıdır. Olağan aritmetik dönüşümlerden sonraki bağımsız değişken türleri, ilgili parametrelerin türleri ile atama uyumlu olmalıdır. (Aritmetik dönüşümler hakkında bilgi için [Olağan Aritmetik](../c-language/usual-arithmetic-conversions.md) Dönüşümler'e bakın.) Elipsleri izleyen bağımsız değişkenler kontrol edilmez. Bir parametrenin herhangi bir temel, yapı, birleşim, işaretçi veya dizi türü olabilir.

Derleyici, her parametrede ve gerekirse her bağımsız değişkende olağan aritmetik dönüşümleri bağımsız olarak gerçekleştirir. Dönüştürmeden sonra, parametre türü `int`prototipte **float** olarak açıkça belirtilmediği sürece hiçbir parametre bir 'den kısa dır ve hiçbir parametre **float** türüne sahip değildir. Bu, örneğin, bir parametreyi bir `char` `int`. olarak bildirmekle aynı etkiye sahip olduğu anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
