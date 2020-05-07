---
title: İşlev Gövdesi
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
ms.openlocfilehash: 2d2e04572de91b161237d999bb95cfda26256c54
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857105"
---
# <a name="function-body"></a>İşlev Gövdesi

*İşlev gövdesi* , işlevin ne yaptığını belirten deyimleri içeren bileşik bir ifadedir.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *bileşik-deyimin*

/\**öznitelik-Seq* , Microsoft 'a özgüdür\*/

*bileşik-ifade*:/\* işlev gövdesi\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-List*<sub>opt</sub> *bildirimini-List*<sub>opt</sub> **}**

*Yerel değişkenler*olarak bilinen bir işlev gövdesinde belirtilen değişkenlerin, aksi belirtilmedikçe **Otomatik** depolama sınıfı vardır. İşlev çağrıldığında Yerel değişkenler için depolama oluşturulur ve yerel başlatma işlemleri gerçekleştirilir. Yürütme denetimi *bileşik deyimdeki* ilk ifadeye geçer ve bir **dönüş** ifadesiyle veya işlev gövdesinin sonuna ulaşana kadar devam eder. Sonra Denetim, işlevin çağrıldığı noktaya döner.

İşlevin bir değer döndürmesi durumunda bir ifade içeren **Return** deyiminin yürütülmesi gerekir. Return **deyimi yoksa** veya **Return** deyimi bir ifade içermiyorsa, bir işlevin dönüş değeri tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
