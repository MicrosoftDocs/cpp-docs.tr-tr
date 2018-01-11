---
title: "Assert işlevinin yazdırdığı tanılama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 243956f1d85b07b5d5b810ebfd112b2cbfe16242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama
**ANSI 4.2** tarafından yazdırılan tanılama ve sonlandırma davranışını **assert** işlevi  
  
 **Assert** işlevi yazdırır bir tanılama iletisi ve çağrıları **abort** ifade yanlışsa yordamına (0). Tanılama iletisi şu formdadır:  
  
 **Onaylama işlemi başarısız**: *ifade***, dosya** *filename***, satır** *linenumber*  
  
 burada dosya adı kaynak dosyanın adıdır, satır numarası kaynak dosyada başarısız onayın satır sayısıdır. İfade doğru (sıfırdan farklı) ise hiçbir eylem gerçekleştirilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık İşlevleri](../c-language/library-functions.md)