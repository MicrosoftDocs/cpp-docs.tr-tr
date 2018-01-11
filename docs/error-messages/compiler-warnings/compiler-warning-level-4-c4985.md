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
ms.workload: cplusplus
ms.openlocfilehash: cb2b95e10a5a5e2b6fcaf67ab41880580267ec7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4985"></a>Derleyici Uyarısı (düzey 4) C4985
'sembol adını': öznitelikler önceki bildiriminde yok.  
  
 Ek açıklamalar önceki bildiriminde Microsoft kaynak kodu ek açıklama dili (SAL) ek açıklamalar geçerli yöntem bildirimi veya tanımı farklıdır. Aynı SAL ek açıklamaları tanımını ve bildirimleri bir yöntemin kullanılması gerekir.  
  
 SAL nasıl bir işlev parametreleri, bunlarla ilgili kolaylaştırır varsayımları ve kolaylaştırır garanti tamamlama üzerinde kullandığı tanımlamak için kullanabileceğiniz ek açıklamaları kümesi sağlar. Ek açıklamalar sal.h üstbilgi dosyasında tanımlanır.  
  
 Proje olmadıkça SAL makroları genişletilemez dikkat edin [/ analyze](../../build/reference/analyze-code-analysis.md) bayrağı belirtilmiş. Belirttiğinizde **/ analyze**, hiçbir uyarı veya hata olmadan görünen olsa bile derleyici C4985, atabilirsiniz **/ analyze**.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Aynı SAL ek açıklamaları bir yöntem ve tüm bildirimleri tanımını kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)