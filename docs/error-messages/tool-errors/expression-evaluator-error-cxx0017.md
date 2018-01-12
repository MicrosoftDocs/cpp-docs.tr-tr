---
title: "İfade değerlendirici hatası CXX0017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0017
dev_langs: C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e769e9886168c9f19ad110c48d848a9b84ab8aac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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