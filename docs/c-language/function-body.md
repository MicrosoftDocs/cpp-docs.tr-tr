---
title: İşlev Gövdesi
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
ms.openlocfilehash: 2ae73ab4ca91e06e3b6cd41166a8d05ae0857e4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229707"
---
# <a name="function-body"></a>İşlev Gövdesi

*İşlev gövdesi* , işlevin ne yaptığını belirten deyimleri içeren bileşik bir ifadedir.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *bileşik-deyimin*

/\**öznitelik-Seq* , Microsoft 'a özgüdür\*/

*bileşik-ifade*:/ \* işlev gövdesi\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-List*<sub>opt</sub> *bildirimini-List*<sub>opt</sub> **}**

*Yerel değişkenler*olarak bilinen bir işlev gövdesinde belirtilen değişkenlerin, **`auto`** Aksi belirtilmediği sürece depolama sınıfı vardır. İşlev çağrıldığında Yerel değişkenler için depolama oluşturulur ve yerel başlatma işlemleri gerçekleştirilir. Yürütme denetimi *bileşik deyimdeki* ilk ifadeye geçer ve bir **`return`** ifade yürütülene veya işlev gövdesinin sonuna ulaşana kadar devam eder. Sonra Denetim, işlevin çağrıldığı noktaya döner.

**`return`** İşlevin bir değer döndürmesi durumunda bir ifade içeren bir deyim yürütülmelidir. Hiçbir **`return`** deyim yoksa veya deyim bir ifade içermiyorsa, bir işlevin dönüş değeri tanımsızdır **`return`** .

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)
