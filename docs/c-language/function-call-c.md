---
title: İşlev Call (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ec4e92774cdec75e47c07407ee72444a7486f7f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751341"
---
# <a name="function-call-c"></a>İşlev Çağrısı (C)

A *işlev çağrısı* , çağrılan işlevin adını veya bir işlev işaretçisi ve isteğe bağlı olarak işleve geçirilen bağımsız değişken değerini içeren bir ifadedir.  
  
## <a name="syntax"></a>Sözdizimi

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi***(***bağımsız değişken ifade listesi*<sub>iyileştirilmiş</sub> **)**   
  
*bağımsız değişken ifade listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/> &nbsp;&nbsp;&nbsp;&nbsp;*bağımsız değişken ifade listesi* **,** *atama ifadesi*  
  
*Sonek ifadesi* bir işlev adresini (örneğin, bir işlev Belirleyicisi veya işlev işaretçisinin değeri) değerlendirmelidir ve *bağımsız değişken ifade listesi* (ayrılmış ifadeler listesi virgülle) değerleri ("değişkenler") işleve geçirilir. *Bağımsız değişken ifade listesi* bağımsız değişkeni boş olabilir.  
  
Bir işlev çağrısı ifadesi, işlevin dönüş değerinin değerine ve türüne sahiptir. Bir işlev dizi türünde bir nesne döndüremez. İşlevin dönüş türü `void` ise (yani işlev hiçbir zaman bir değer döndürmeyecek şekilde bildirilmişse), işlev çağrısı ifadesinde de `void` türü vardır. (Bkz [işlev çağrıları](../c-language/function-calls.md) daha fazla bilgi için.)  
  
## <a name="see-also"></a>Ayrıca Bkz.

[İşlev Çağırma İşleci: ()](../cpp/function-call-operator-parens.md)