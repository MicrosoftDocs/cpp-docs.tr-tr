---
title: Komut satırı uyarısı D9027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfe2493290c4e4cc5b744136b8e7036c6559220a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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