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
ms.workload: cplusplus
ms.openlocfilehash: 2769eb5f78cb1d5bdd6749e65429d83b69a2807b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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