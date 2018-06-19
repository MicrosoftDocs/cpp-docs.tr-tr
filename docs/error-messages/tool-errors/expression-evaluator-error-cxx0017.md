---
title: İfade değerlendirici hatası CXX0017 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0017
dev_langs:
- C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7540dc701ffa6e0acb3d2661e1196e5f4552d2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300756"
---
# <a name="expression-evaluator-error-cxx0017"></a>İfade Değerlendirici Hatası CXX0017
Sembol bulunamadı  
  
 Bir deyim içinde belirtilen bir simge bulunamadı.  
  
 Bu hatanın olası bir nedeni bir simge adı büyük/küçük harfe eşleşmemesidir. C ve C++ büyük küçük harfe duyarlı dilleri olduğundan, kaynak olarak tanımlandığı tam durumda bir simge adı verilmesi gerekir.  
  
 Bu hata, hata ayıklama sırasında değişkeni izlemek için bir değişken typecast çalıştığınızda oluşabilir. `typedef` Bir tür için yeni bir ad bildirir, ancak yeni bir tür tanımlamıyor. Hata ayıklayıcıda çalıştı typecast tanımlanmış bir türü adı gerektirir.  
  
 Bu hata için CAN0017 aynıdır.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Simgenin zaten burada kullanılıyor programı noktada bildirildiğinden emin olun.  
  
2.  Hata Ayıklayıcısı'ndaki değişkenler yayınlanamıyor gerçek tür adı kullanmak yerine bir `typedef`-adı tanımlı.