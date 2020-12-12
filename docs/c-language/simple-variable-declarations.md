---
description: 'Daha fazla bilgi edinin: basit değişken bildirimleri'
title: Basit Değişken Bildirimler
ms.date: 11/04/2016
helpviewer_keywords:
- untyped variables
- declaring variables, simple
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
ms.openlocfilehash: ccb63ad3726d8a5ed5692abd5ec678a1b517614d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114630"
---
# <a name="simple-variable-declarations"></a>Basit Değişken Bildirimler

Basit bir değişkenin bildirimi, bir doğrudan bildirimci için en basit form, değişkenin adını ve türünü belirtir. Ayrıca, değişkenin depolama sınıfını ve veri türünü de belirtir.

Değişken bildirimlerinde Depolama sınıfları veya türleri (veya her ikisi de) gereklidir. Türsüz değişkenler (gibi `var;` ) uyarı oluşturur.

## <a name="syntax"></a>Syntax

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*

*tanımlayıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*rakam olmayan*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *basamak olmayan*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *sayısı*

Aritmetik, yapı, birleşim, numaralandırmalar ve void türler için ve adlara göre temsil edilen türler için **`typedef`** , tür belirleyicisi tüm yazma bilgilerini sağladığı için bir bildirimde basit Bildirimciler kullanılabilir. İşaretçi, dizi ve işlev türleri daha karmaşık Bildirimciler gerektirir.

Aynı bildirimde birkaç değişken belirtmek için virgülle (**,**) ayrılan tanımlayıcıların bir listesini kullanabilirsiniz. Bildirimde tanımlanan tüm değişkenler aynı temel türe sahip. Örneğin:

```C
int x, y;        /* Declares two simple variables of type int */
int const z = 1; /* Declares a constant value of type int */
```

Değişkenler `x` ve `y` **`int`** belirli bir uygulama için türü tarafından tanımlanan küme içinde herhangi bir değeri tutabilir. Basit nesne `z` 1 değerine başlatılır ve değiştirilebilir değildir.

Bildirimi `z` başlatılmamış bir statik değişken için ise veya dosya kapsamımda olsaydı, 0 başlangıç değerini alır ve bu değer değiştirilemez.

```C
unsigned long reply, flag; /* Declares two variables
                              named reply and flag     */
```

Bu örnekte, ve öğelerinin her ikisi de `reply` `flag` **`unsigned long`** türünde ve işaretsiz tam sayı değerlerini tutar.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md)
