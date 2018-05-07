---
title: İfade değerlendirici hatası CXX0045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0045
dev_langs:
- C++
helpviewer_keywords:
- CXX0045
- CAN0045
ms.assetid: 32181bc8-e79c-4ad7-a82f-47c62ec06d7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac52b16c2c8551282b79ef6a7fda40e24acc6bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0045"></a>İfade Değerlendirici Hatası CXX0045
bir işlev değil  
  
 Bir bağımsız değişken listesi bir işlevin adını değil program dosyasındaki bir simge için sağlandı.  
  
## <a name="example"></a>Örnek  
  
```  
queue( alpha, beta )  
```  
  
 zaman `queue` bir işlev değil.  
  
 Bu hata için CAN0045 aynıdır.