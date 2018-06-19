---
title: Derleyici Uyarısı (düzey 4) C4985 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8f0b62a72d61ee061fd996f93638acba9e7ebb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301096"
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