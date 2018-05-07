---
title: İfade değerlendirici hatası CXX0036 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0036
dev_langs:
- C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18e1bf3cda85d7b3d64d51279688a52cec5c0336
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0036"></a>İfade Değerlendirici Hatası CXX0036
bozuk içerik {...} belirtim  
  
 Bu ileti bağlamı işleci kullanımı çeşitli hatalar hiçbiri tarafından oluşturulan (**{}**).  
  
-   Context işleci söz dizimi (**{}**) yanlış verildi.  
  
     Context işleci sözdizimi şöyledir:  
  
     {*işlevi*,*Modülü*,*dll*}*ifade*  
  
     Bu bağlamı belirtir *ifade*. Context işleci aynı öncelik ve kullanım bir cast türünü sahiptir.  
  
     Virgül sondaki atlanabilir. Varsa *işlevi*, *Modülü*, veya *dll* değişmez değer virgül içeren adın tamamını parantez içine alın.  
  
-   İşlev adı yanlış yazılmış veya belirtilen modül veya dinamik bağlantı kitaplığı yok.  
  
     Büyük küçük harfe duyarlı bir dil C olduğu için *işlevi* kaynağında tanımlanan tam durumda verilmelidir.  
  
-   Modüle ya da DLL bulunamadı.  
  
     Belirtilen modül veya DLL tam yol adını kontrol edin.  
  
 Bu hata için CAN0036 aynıdır.