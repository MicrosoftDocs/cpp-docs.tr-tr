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
ms.openlocfilehash: 49c9483cb6e556d5a8b174377c0dad666834c9e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384365"
---
# <a name="function-call-c"></a>İşlev Çağrısı (C)
"İşlev çağrısı", çağrılan işlevin adını veya bir işlev işaretçisinin adını ve isteğe bağlı olarak işlevine geçirilen bağımsız değişkenleri içeren bir ifadedir.  
  
## <a name="syntax"></a>Sözdizimi  
 *sonek ifade*:  
 *sonek ifade***(***bağımsız değişken ifadesi listesi* kabul **)**   
  
 *bağımsız değişken ifadesi listesi*:  
 *atama ifadesi*  
  
 *bağımsız değişken ifadesi listesi***,***atama ifadesi*   
  
 *Sonek ifade* bir işlev adresi (örneğin, bir işlev tanımlayıcısı veya bir işlev işaretçisi değerini) değerlendirmeniz gerekir ve *bağımsız değişken ifadesi listesi* ifadeleri (ayrılmış bir listesi virgül tarafından) değerleri ("değişkenler") işlevine geçirilir. *Bağımsız değişken ifadesi listesi* bağımsız değişkeni boş olamaz.  
  
 Bir işlev çağrısı ifadesi, işlevin dönüş değerinin değerine ve türüne sahiptir. Bir işlev dizi türünde bir nesne döndüremez. İşlevin dönüş türü `void` ise (yani işlev hiçbir zaman bir değer döndürmeyecek şekilde bildirilmişse), işlev çağrısı ifadesinde de `void` türü vardır. (Bkz [işlev çağrılarını](../c-language/function-calls.md) daha fazla bilgi için.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev Çağırma İşleci: ()](../cpp/function-call-operator-parens.md)