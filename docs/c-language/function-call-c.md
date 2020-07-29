---
title: İşlev Çağrısı (C)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
ms.openlocfilehash: 23531f25128fc267caa3a3cad5f2c52e603a2cc6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229694"
---
# <a name="function-call-c"></a>İşlev Çağrısı (C)

*İşlev çağrısı* , çağrılan işlevin adını veya bir işlev işaretçisinin değerini içeren bir ifadedir ve isteğe bağlı olarak, işleve geçirilen bağımsız değişkenleri.

## <a name="syntax"></a>Sözdizimi

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **(**  *bağımsız değişken-ifade-List*<sub>opt</sub> **)**

*bağımsız değişken-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bağımsız değişken-ifade listesi* **,** *atama ifadesi*

*Sonek ifadesi* bir işlev adresi (örneğin, bir işlev tanımlayıcısı veya bir işlev işaretçisinin değeri) olarak değerlendirilmelidir ve *bağımsız değişken-ifade listesi* , değerleri ("arguments") işlevine geçirilir (virgülle ayrılmış). *Bağımsız değişken-ifade listesi* bağımsız değişkeni boş olabilir.

Bir işlev çağrısı ifadesi, işlevin dönüş değerinin değerine ve türüne sahiptir. Bir işlev dizi türünde bir nesne döndüremez. İşlevin dönüş türü ise **`void`** (diğer bir deyişle, işlev bir değer döndürmek için hiçbir şekilde bildirilmiştir), işlev çağrısı ifadesinin türü de vardır **`void`** . (Daha fazla bilgi için bkz. [Işlev çağrıları](../c-language/function-calls.md) .)

## <a name="see-also"></a>Ayrıca bkz.

[İşlev çağırma Işleci: ()](../cpp/function-call-operator-parens.md)
