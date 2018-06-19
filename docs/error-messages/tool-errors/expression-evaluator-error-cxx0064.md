---
title: İfade değerlendirici hatası CXX0064 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7964eac628fa89695d1757cff8b7b329fd7fe713
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302142"
---
# <a name="expression-evaluator-error-cxx0064"></a>İfade Değerlendirici Hatası CXX0064
kesme noktası üzerinde sanal üye sınır işlevi ayarlanamıyor  
  
 Bir kesme noktası bir nesne için bir işaretçi aracılığıyla sanal üye işlevi üzerinde gibi ayarlandı:  
  
```  
pClass->vfunc( int );  
```  
  
 Bir kesme noktası üzerinde bir sanal işlev sınıfı gibi girerek ayarlanabilir:  
  
```  
Class::vfunc( int );  
```  
  
 Bu hata için CAN0064 aynıdır.