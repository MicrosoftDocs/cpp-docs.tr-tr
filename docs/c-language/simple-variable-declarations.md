---
title: Basit Değişken Bildirimler
ms.date: 11/04/2016
helpviewer_keywords:
- untyped variables
- declaring variables, simple
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
ms.openlocfilehash: 27710dabe512332564ee557a9d022457d9fddc5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158242"
---
# <a name="simple-variable-declarations"></a>Basit Değişken Bildirimler

Basit bir değişkenin bildirimi, bir doğrudan bildirimci için en basit form, değişkenin adını ve türünü belirtir. Ayrıca, değişkenin depolama sınıfını ve veri türünü de belirtir.

Değişken bildirimlerinde Depolama sınıfları veya türleri (veya her ikisi de) gereklidir. Türsüz değişkenler (gibi `var;`) uyarı oluşturur.

## <a name="syntax"></a>Sözdizimi

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*

*tanımlayıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*rakam olmayan*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *basamak olmayan*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *sayısı*

Aritmetik, yapı, birleşim, numaralandırmalar ve void türler için ve adlara göre `typedef` temsil edilen türler için, tür belirleyicisi tüm yazma bilgilerini sağladığı için bir bildirimde basit Bildirimciler kullanılabilir. İşaretçi, dizi ve işlev türleri daha karmaşık Bildirimciler gerektirir.

Aynı bildirimde birkaç değişken belirtmek için virgülle (**,**) ayrılan tanımlayıcıların bir listesini kullanabilirsiniz. Bildirimde tanımlanan tüm değişkenler aynı temel türe sahip. Örneğin:

```C
int x, y;        /* Declares two simple variables of type int */
int const z = 1; /* Declares a constant value of type int */
```

Değişkenler `x` ve `y` belirli bir uygulama için `int` türü tarafından tanımlanan küme içinde herhangi bir değeri tutabilir. Basit nesne `z` 1 değerine başlatılır ve değiştirilebilir değildir.

Bildirimi `z` başlatılmamış bir statik değişken için ise veya dosya kapsamımda olsaydı, 0 başlangıç değerini alır ve bu değer değiştirilemez.

```C
unsigned long reply, flag; /* Declares two variables
                              named reply and flag     */
```

Bu örnekte, `reply` ve `flag`öğelerinin her ikisi de `unsigned long` türünde ve işaretsiz tam sayı değerlerini tutar.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)
