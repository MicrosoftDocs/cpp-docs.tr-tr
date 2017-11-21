---
title: "İşlev Call (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0faf339877b075a1337c73ec5ca3c41a869ceec2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="function-call-c"></a>İşlev Çağrısı (C)
"İşlev çağrısı", çağrılan işlevin adını veya bir işlev işaretçisinin adını ve isteğe bağlı olarak işlevine geçirilen bağımsız değişkenleri içeren bir ifadedir.  
  
## <a name="syntax"></a>Sözdizimi  
 *sonek ifade*:  
 *sonek ifade***(***bağımsız değişken ifadesi listesi* kabul**)**   
  
 *bağımsız değişken ifadesi listesi*:  
 *atama ifadesi*  
  
 *bağımsız değişken ifadesi listesi***,***atama ifadesi*   
  
 *Sonek ifade* bir işlev adresi (örneğin, bir işlev tanımlayıcısı veya bir işlev işaretçisi değerini) değerlendirmeniz gerekir ve *bağımsız değişken ifadesi listesi* ifadeleri (ayrılmış bir listesi virgül tarafından) değerleri ("değişkenler") işlevine geçirilir. *Bağımsız değişken ifadesi listesi* bağımsız değişkeni boş olamaz.  
  
 Bir işlev çağrısı ifadesi, işlevin dönüş değerinin değerine ve türüne sahiptir. Bir işlev dizi türünde bir nesne döndüremez. İşlevin dönüş türü `void` ise (yani işlev hiçbir zaman bir değer döndürmeyecek şekilde bildirilmişse), işlev çağrısı ifadesinde de `void` türü vardır. (Bkz [işlev çağrılarını](../c-language/function-calls.md) daha fazla bilgi için.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev çağırma işleci:)](../cpp/function-call-operator-parens.md)