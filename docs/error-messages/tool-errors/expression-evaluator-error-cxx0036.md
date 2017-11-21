---
title: "İfade değerlendirici hatası CXX0036 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0036
dev_langs: C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58d5fa976306c6e8a2545ce852bf3e808bc5b2d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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