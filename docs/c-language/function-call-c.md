---
title: İşlev Çağrısı (C)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
ms.openlocfilehash: d22bdebc8fa832afb14a2cc09e6a441b7b9e8a5a
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147418"
---
# <a name="function-call-c"></a>İşlev Çağrısı (C)

A *işlev çağrısı* , çağrılan işlevin adını veya bir işlev işaretçisi ve isteğe bağlı olarak işleve geçirilen bağımsız değişken değerini içeren bir ifadedir.

## <a name="syntax"></a>Sözdizimi

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi* **(** *bağımsız değişken ifade listesi*<sub>iyileştirilmiş</sub> **)**

*bağımsız değişken ifade listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*argument-expression-list* **,** *assignment-expression*

*Sonek ifadesi* bir işlev adresini (örneğin, bir işlev Belirleyicisi veya işlev işaretçisinin değeri) değerlendirmelidir ve *bağımsız değişken ifade listesi* (ayrılmış ifadeler listesi virgülle) değerleri ("değişkenler") işleve geçirilir. *Bağımsız değişken ifade listesi* bağımsız değişkeni boş olabilir.

Bir işlev çağrısı ifadesi, işlevin dönüş değerinin değerine ve türüne sahiptir. Bir işlev dizi türünde bir nesne döndüremez. İşlevin dönüş türü `void` ise (yani işlev hiçbir zaman bir değer döndürmeyecek şekilde bildirilmişse), işlev çağrısı ifadesinde de `void` türü vardır. (Bkz [işlev çağrıları](../c-language/function-calls.md) daha fazla bilgi için.)

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Çağırma İşleci: ()](../cpp/function-call-operator-parens.md)
