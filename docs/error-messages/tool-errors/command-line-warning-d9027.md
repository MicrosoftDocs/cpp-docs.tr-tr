---
title: "Komut satırı uyarısı D9027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9027
dev_langs: C++
helpviewer_keywords: D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5ccdccbc4c6df8f948b44eeaa096cff46824d043
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="command-line-warning-d9027"></a>Komut Satırı Uyarısı D9027
kaynak dosyası '\<dosya adı >' yoksayıldı  
  
 CL.exe giriş kaynak dosyası yoksayıldı.  
  
 Bu uyarı /Fo seçeneği ile /c seçeneği ile komut satırında bir çıktı filename arasında bir boşluk neden olabilir. Örneğin:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 /Fo arasında bir boşluk olduğundan ve `output.obj`, CL.exe geçen `output.obj` adı olarak giriş dosyası. Sorunu düzeltmek için alanı kaldırın:  
  
```  
cl /c /Fooutput.obj input.c   
```