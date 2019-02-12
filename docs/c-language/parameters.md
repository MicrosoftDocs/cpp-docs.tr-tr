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
ms.openlocfilehash: 0652fe6076899020050d94378649018721b4b188
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147236"
---
# <a name="parameters"></a>Parametreler

Bağımsız değişkenler, işlev çağrısına göre bir işleve geçirilen değerlerin adlarıdır. Parametreler işlevi almak için bekliyor değerlerdir. Bir işlev prototipi işlev adının parantez işlevin parametreleri ve bunların türlerini tam bir listesi bulunur. Parametre bildirimi, türleri, boyutları ve parametreler depolanan değerlerin tanımlayıcıları belirtir.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> *öznitelik-seq*<sub>iyileştirilmiş</sub> *bildirimci* *bildirim listesi*  <sub>iyileştirilmiş</sub> *bileşik deyim*

/\* *öznitelik-seq* Microsoft Specific \*/

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*: /\* işlev bildirimcisi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci***(***parametre türü listesi***)**  / \* yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci***(***tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**  / \* Kullanımdan kalktı stili bildirimci \*/

*parametre türü listesi*: /\* parametre listesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,...**

*parametre listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,***parametre bildirimi*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *bildirimcisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *soyut bildirimci*<sub>iyileştirilmiş</sub>

*Parametre türü listesi* virgülle ayırarak parametre bildirimleri oluşan bir dizidir. Bir parametre listesindeki her bir parametre biçimi şöyle görünür:

```C
[register]  type-specifier [declarator]
```

İşlev parametreleri ile bildirilmiş **otomatik** özniteliği hatalar oluşturun. Tanımlayıcıları parametrelerin işlev gövdesinde işleve geçirilen değerlerin başvurmak için kullanılır. Bir prototipteki parametreleri adlandırabilirsiniz, ancak adları, bildirim sonunda kapsam dışına. Bu nedenle parametre adları aynı şekilde veya farklı işlev tanımında atanabilir. Bu tanımlayıcılar işlev gövdesinin en dıştaki bloğunun içinde tanımlanamaz, ancak parametre listesi gibi davranarak kapsayan bir blok iç, iç içe geçmiş bloklarında tanımlanabilir.

Her bir tanımlayıcının *parametre türü listesi* Bu örnekte gösterildiği gibi uygun tür belirticisi tarafından öncesinde olmalıdır:

```C
void new( double x, double y, double z )
{
    /* Function body here */
}
```

En az bir parametre parametre listesinde ortaya çıkarsa, liste üç nokta bir virgül ile sona erdirebilirsiniz (**,...** ). "Üç nokta gösterimi," olarak adlandırılan bu yapı, işlev bağımsız değişken sayıda gösterir. (Bkz [bir değişken sayıda bağımsız değişkenli çağrılar](../c-language/calls-with-a-variable-number-of-arguments.md) daha fazla bilgi için.) Ancak, son virgülden önceki parametreleri olduğundan, en az sayıda bağımsız değişken işlevine bir çağrı olması gerekir.

İşleve geçirilecek bağımsız değişken olmadan olması durumunda, parametre listesi anahtar sözcüğü değiştirilir `void`. Bu kullanımı `void` bir tür tanımlayıcısı olarak kullanımı öğesinden farklıdır.

Üç nokta gösterimi kullanımı dahil olmak üzere, parametre türüne ve sırası (varsa) ilgili tüm işlev bildirimleri ve işlev tanımında'de aynı olması gerekir. Olağan aritmetik dönüştürmeler atama ile uyumlu olmalıdır. sonra bağımsız değişkenlerinin türlerine karşılık gelen parametre türleri ile. (Bkz [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) aritmetik dönüştürmeleri hakkında bilgi için.) Aşağıdaki üç bağımsız değişken denetlenmez. Bir parametre, yapı, birleşim, işaretçi, tüm temel sahip veya dizi türü.

Derleyici olağan aritmetik dönüştürmeler bağımsız olarak her bir parametre ve her bağımsız değişken gerekirse gerçekleştirir. Dönüştürme işleminden sonra hiçbir parametre türünden daha kısa bir `int`, ve bir parametre yok **float** parametre türü olarak açıkça belirtilmediği sürece yazın **float** prototipteki. Bu, örneğin, bu parametre olarak bildirme anlamına gelir bir `char` olarak bildirme aynı etkiye sahip bir `int`.

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
