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
ms.workload: cplusplus
ms.openlocfilehash: fdf6ddf412786a53ec8da995c2824274da2da3b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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