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

Doğrudan bir bildirimcide en basit biçimi basit bir değişkenin bildirimi, değişkenin adını ve türünü belirtir. Ayrıca, değişken depolama sınıfı ve veri türünü belirtir.

Depolama sınıfları veya türleri (veya her ikisi) değişken bildirimlerinde gerekir. Türsüz değişkenleri (gibi `var;`) uyarı oluşturur.

## <a name="syntax"></a>Sözdizimi

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*

*tanımlayıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*rakam*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *rakam*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *basamak*

Tarafından temsil edilen türleri yanı sıra, aritmetik, yapı, birleşim, numaralandırmalar ve void türleri için `typedef` adları, basit Bildirimciler tür belirticisi yazma tüm bilgileri sağlayan bu yana bir bildiriminde kullanılabilir. Daha karmaşık bildirimcileri işaretçisi, dizi ve işlev türleri gerektirir.

Virgülle ayırarak tanımlayıcıları listesini kullanabilirsiniz (**,**) çeşitli değişkenler aynı bildirimde belirtmek için. Bildiriminde tanımlanan tüm değişkenler aynı temel türüne sahip. Örneğin:

```C
int x, y;        /* Declares two simple variables of type int */
int const z = 1; /* Declares a constant value of type int */
```

Değişkenleri `x` ve `y` herhangi bir değer tarafından tanımlanan kümeye de barındırabilir `int` türü için belirli bir uygulama. Basit Nesne `z` değeri 1 başlatılır ve değiştirilemez.

Varsa bildirimi `z` başlatılmamış bir statik değişken için olan ya da dosya kapsamında başlangıç değeri 0 olarak alırsınız ve bu değer değiştirilemeyen olacaktır.

```C
unsigned long reply, flag; /* Declares two variables
                              named reply and flag     */
```

Bu örnekte, her iki değişken `reply` ve `flag`, sahip `unsigned long` yazın ve işaretsiz tamsayı değerleri tutun.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)
