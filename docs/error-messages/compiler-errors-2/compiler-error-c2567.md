---
title: "Derleyici Hatası C2567 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2567
dev_langs: C++
helpviewer_keywords: C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bbdc535f75230da05a92eb0498176da40e918ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2567"></a>Derleyici Hatası C2567
meta verilerde 'dosya' açılamıyor, dosya taşınmış veya silinmiş  
  
 Kaynağında başvuruldu bir meta veri dosyası (ile `#using`) derleyici ön uç işlemiyle olduğu gibi aynı dizinde tarafından derleyici arka plan işlemi bulunamadı. Bkz: [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) daha fazla bilgi için.  
  
 İle derleme yaparsanız C2567 nedeni olabilir **/c** bir makine ve başka bir makine üzerinde bağlama zamanı kodu oluşturma denemesi. Daha fazla bilgi için bkz: [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 Ayrıca, bilgisayarınız daha fazla bellek olduğunu gösterebilir.  
  
 Bu hatayı düzeltmek için meta veri dosyası oluşturma işlemi tüm aşamalar için dizin konumda olduğundan emin olun.