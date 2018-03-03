---
title: "Basit değişken bildirimler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- untyped variables
- declaring variables, simple
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18798941b227a5da4248b7b44179cb99e3c7d5d9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="simple-variable-declarations"></a>Basit Değişken Bildirimler
Doğrudan bildirimcisi en basit biçimi basit bir değişken bildirimi, değişkenin adını ve türünü belirtir. Ayrıca değişkenin depolama sınıfı ve veri türünü belirtir.  
  
 Depolama sınıfları veya türleri (veya her ikisi de) değişken bildirimlerinde gereklidir. Türsüz değişkenleri (gibi `var;`) uyarılar oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
 `declarator`:  
 *İşaretçi* iptal et  
  
 *doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*:  
 *tanımlayıcı*  
  
 *tanımlayıcı*:  
 *sayı olmayan*  
  
 *tanımlayıcı sayı olmayan*  
  
 *tanımlayıcı basamak*  
  
 Tarafından temsil edilen türleri ve aritmetik, yapısı, UNION, numaralandırmalar ve void türleri için `typedef` adları, basit Bildirimciler tür belirteci yazarak tüm bilgileri sağlayan bu yana bir bildiriminde kullanılabilir. İşaretçi, dizi ve işlev türleri daha karmaşık bildirimcileri gerektirir.  
  
 Tanımlayıcıları virgülle ayrılmış listesi kullanabilirsiniz (**,**) çeşitli değişkenler aynı bildiriminde belirtmek için. Bildiriminde tanımlanan tüm değişkenler aynı temel türe sahip. Örneğin:  
  
```  
int x, y;        /* Declares two simple variables of type int */  
int const z = 1; /* Declares a constant value of type int */  
```  
  
 Değişkenleri `x` ve `y` tarafından tanımlanan kümesindeki herhangi bir değer tutabilir `int` belirli bir uygulama türü. Basit Nesne `z` 1 değerine başlatılır ve değiştirilemez.  
  
 Varsa bildirimi `z` için başlatılmamış bir statik değişkeni ederken veya dosya kapsamda başlangıç değeri 0 olarak alacağı ve bu değer değiştirilemeyen olacaktır.  
  
```  
unsigned long reply, flag; /* Declares two variables  
                              named reply and flag     */  
```  
  
 Bu örnekte, her iki değişken `reply` ve `flag`, sahip `unsigned long` yazın ve imzasız tam sayı değerleri tutun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)