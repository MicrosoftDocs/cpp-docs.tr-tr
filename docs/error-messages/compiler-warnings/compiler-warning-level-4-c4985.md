---
title: "Derleyici Uyarısı (düzey 4) C4985 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af8717f8b821311814a8aa4ee2f5b3e6ead89eef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4985"></a>Derleyici Uyarısı (düzey 4) C4985
'sembol adını': öznitelikler önceki bildiriminde yok.  
  
 Ek açıklamalar önceki bildiriminde Microsoft kaynak kodu ek açıklama dili (SAL) ek açıklamalar geçerli yöntem bildirimi veya tanımı farklıdır. Aynı SAL ek açıklamaları tanımını ve bildirimleri bir yöntemin kullanılması gerekir.  
  
 SAL nasıl bir işlev parametreleri, bunlarla ilgili kolaylaştırır varsayımları ve kolaylaştırır garanti tamamlama üzerinde kullandığı tanımlamak için kullanabileceğiniz ek açıklamaları kümesi sağlar. Ek açıklamalar sal.h üstbilgi dosyasında tanımlanır.  
  
 Proje olmadıkça SAL makroları genişletilemez dikkat edin [/ analyze](../../build/reference/analyze-code-analysis.md) bayrağı belirtilmiş. Belirttiğinizde **/ analyze**, hiçbir uyarı veya hata olmadan görünen olsa bile derleyici C4985, atabilirsiniz **/ analyze**.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Aynı SAL ek açıklamaları bir yöntem ve tüm bildirimleri tanımını kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SAL ek açıklamaları](../../c-runtime-library/sal-annotations.md)