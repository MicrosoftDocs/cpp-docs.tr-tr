---
title: İşlev gövdesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d30cb5429ebee0738aa7b7aab367d79867e92047
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757825"
---
# <a name="function-body"></a>İşlev Gövdesi

A *işlev gövdesi* olan işlevin ne yaptığını belirten deyimleri içeren bir bileşik deyim.

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> *öznitelik-seq*<sub>iyileştirilmiş</sub> *bildirimci* *bildirim listesi*  <sub>iyileştirilmiş</sub> *bileşik deyim*

/\* *öznitelik-seq* Microsoft Specific \*/

*Bileşik deyim*: /\* işlev gövdesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *bildirim listesi*<sub>iyileştirilmiş</sub> *deyim listesindeki*<sub>iyileştirilmiş</sub> **}**

Değişkenler olarak bilinen bir işlev gövdesindeki *yerel değişkenler*, sahip **otomatik** aksi belirtilmediği sürece depolama sınıfı. İşlev çağrıldığında, depolama, yerel değişkenleri oluşturulur ve yerel başlatmalar gerçekleştirilir. Yürütme denetimi geçtiği ilk deyimde *compound-statement* ve kadar devam eder. bir **dönüş** deyimi yürütüldüğünde veya işlev gövdesinin sonuna karşılaşıldı. Denetim, ardından işlev çağrıldı noktasını döndürür.

A **dönüş** içeren bir ifade deyimi gereken yürütülebilir işlev bir değer döndürmek için ise. Öyle değilse bir işlevin dönüş değeri tanımsızdır **dönüş** deyimi yürütüldüğünde veya **dönüş** bir ifade deyimi içermez.

## <a name="see-also"></a>Ayrıca Bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)