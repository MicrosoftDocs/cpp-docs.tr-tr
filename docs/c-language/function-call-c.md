---
title: İşlev Çağrısı (C)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
ms.openlocfilehash: d22bdebc8fa832afb14a2cc09e6a441b7b9e8a5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233304"
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

Bir işlev çağrısı ifadesi, işlevin dönüş değerinin değerine ve türüne sahiptir. Bir işlev dizi türünde bir nesne döndüremez. İşlevin dönüş türü `void` ise (yani işlev hiçbir zaman bir değer döndürmeyecek şekilde bildirilmişse), işlev çağrısı ifadesinde de `void` türü vardır. (Daha fazla bilgi için bkz. [Işlev çağrıları](../c-language/function-calls.md) .)

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Çağırma İşleci: ()](../cpp/function-call-operator-parens.md)
