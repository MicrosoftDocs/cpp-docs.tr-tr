---
description: 'Daha fazla bilgi edinin: Işlev gövdesi'
title: İşlev Gövdesi
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
ms.openlocfilehash: 098a759a8fd4fd9ab69e487ab84f7ed7d0d2c25c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195989"
---
# <a name="function-body"></a>İşlev Gövdesi

*İşlev gövdesi* , işlevin ne yaptığını belirten deyimleri içeren bileşik bir ifadedir.

## <a name="syntax"></a>Syntax

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *bileşik-deyimin*

/\**öznitelik-Seq* , Microsoft 'a özgüdür\*/

*bileşik-ifade*:/ \* işlev gövdesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-List*<sub>opt</sub> *bildirimini-List*<sub>opt</sub> **}**

*Yerel değişkenler* olarak bilinen bir işlev gövdesinde belirtilen değişkenlerin, **`auto`** Aksi belirtilmediği sürece depolama sınıfı vardır. İşlev çağrıldığında Yerel değişkenler için depolama oluşturulur ve yerel başlatma işlemleri gerçekleştirilir. Yürütme denetimi *bileşik deyimdeki* ilk ifadeye geçer ve bir **`return`** ifade yürütülene veya işlev gövdesinin sonuna ulaşana kadar devam eder. Sonra Denetim, işlevin çağrıldığı noktaya döner.

**`return`** İşlevin bir değer döndürmesi durumunda bir ifade içeren bir deyim yürütülmelidir. Hiçbir **`return`** deyim yoksa veya deyim bir ifade içermiyorsa, bir işlevin dönüş değeri tanımsızdır **`return`** .

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)
