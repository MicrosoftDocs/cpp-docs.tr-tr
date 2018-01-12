---
title: "İfade değerlendirici hatası CXX0064 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0064
dev_langs: C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2edeb05e39c6d2e70cb2c9dde562a89e85921301
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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