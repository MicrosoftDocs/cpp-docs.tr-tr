---
description: 'Daha fazla bilgi edinin: parametreler'
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
ms.openlocfilehash: b68cd5934e597e486b00f2772e913f627e584ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256828"
---
# <a name="parameters"></a>Parametreler

Bağımsız değişkenler bir işleve işlev çağrısı tarafından geçirilen değerlerin adlarıdır. Parametreler, işlevin almayı beklediği değerlerdir. Bir işlev prototipinden, işlev adını izleyen parantezler işlevin parametrelerinin ve türlerinin tamamen bir listesini içerir. Parametre bildirimleri, parametrelerde depolanan değerlerin türlerini, boyutlarını ve tanımlayıcılarını belirler.

## <a name="syntax"></a>Syntax

*`function-definition`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declaration-specifiers`*<sub>opt</sub> *`attribute-seq`* <sub>opt</sub> *`declarator`* *`declaration-list`* <sub>opt</sub>*`compound-statement`*

/\**`attribute-seq`* Microsoft 'a özgü\*/

*`declarator`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`pointer`*<sub>opt</sub>*`direct-declarator`*

*`direct-declarator`*:/ \* Bir işlev bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`direct-declarator`*  **`(`**  *`parameter-type-list`*  **`)`** /\* Yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`direct-declarator`*  **`(`**  *`identifier-list`*<sub></sub> **`)`**  / opt \* Eski stil bildirimci\*/

*`parameter-type-list`*:/ \* Parametre listesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`parameter-list`* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`parameter-list`* **`, ...`**

*`parameter-list`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`parameter-declaration`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`parameter-list`* **`,`**  *`parameter-declaration`*

*`parameter-declaration`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declaration-specifiers`* *`declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declaration-specifiers`**`abstract-declarator`* <sub>opt</sub>

, *`parameter-type-list`* Virgülle ayrılmış bir parametre bildirimleri dizisidir. Bir parametre listesindeki her parametrenin biçimi şöyle görünür:

> **`register`**<sub>opt</sub> *`type-specifier`* *`declarator`* <sub>opt</sub>

Öznitelik oluşturma hatası ile belirtilen işlev parametreleri **`auto`** . Parametre tanımlayıcıları, işleve geçirilen değerlere başvurmak için işlev gövdesinde kullanılır. Bir prototipde parametreleri isimlendirebilmeniz, ancak adlar bildirimin sonundaki kapsam dışına çıkar. Bu, parametre adlarının işlev tanımına aynı şekilde veya farklı şekilde atanabileceği anlamına gelir. Bu tanımlayıcılar, işlev gövdesinin en dıştaki bloğunda yeniden tanımlanamaz, ancak parametre listesi kapsayan bir blok olmasına rağmen iç, iç içe bloklar içinde yeniden tanımlanabilir.

İçindeki her tanımlayıcı *`parameter-type-list`* , bu örnekte gösterildiği gibi önce uygun tür belirticisinden gelmelidir:

```C
void new( double x, double y, double z )
{
    /* Function body here */
}
```

Parametre listesinde en az bir parametre oluşursa, liste bir virgül ile ve ardından üç nokta () ile bitebilirler **`, ...`** . "Üç nokta gösterimi" olarak adlandırılan bu yapım, işlev için değişken sayıda bağımsız değişken belirtir. (Daha fazla bilgi için bkz. [değişken sayıda bağımsız değişken Içeren çağrılar](../c-language/calls-with-a-variable-number-of-arguments.md).) Ancak, bir işlev çağrısının en az sayıda bağımsız değişkeni olması gerekir ve bu, son virgülden önce parametre vardır.

İşleve hiçbir bağımsız değişken geçirilmezse, parametrelerin listesi, anahtar sözcüğüyle değiştirilmiştir **`void`** . Bu kullanımı, **`void`** bir tür belirleyici olarak kullanımıyla farklıdır.

Üç nokta gösteriminin kullanımı dahil olmak üzere parametrelerin sırası ve türü, tüm işlev bildirimlerinde ve işlev tanımında aynı olmalıdır. Her zamanki aritmetik dönüşümlerden sonraki bağımsız değişkenlerin türleri, karşılık gelen parametrelerin türleriyle atama ile uyumlu olmalıdır. (Aritmetik dönüştürmeler hakkında bilgi için bkz. [normal aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) .) Üç noktayı izleyen bağımsız değişkenler işaretlenmemektedir. Bir parametre herhangi bir temel, yapı, birleşim, işaretçi veya dizi türüne sahip olabilir.

Derleyici, her bir parametrede ve gerekirse her bağımsız değişkende her zaman bağımsız olarak her bir aritmetik dönüştürme gerçekleştirir. Dönüştürmeden sonra, hiçbir parametre bir değerden daha kısadır **`int`** ve **`float`** parametre türü açıkça prototipi olarak belirtilmedikçe hiçbir parametre türü yoktur **`float`** . Örneğin, bir parametreyi bir olarak bildirme gibi, bir parametresi olarak bildirme anlamına gelir **`char`** **`int`** .

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)
