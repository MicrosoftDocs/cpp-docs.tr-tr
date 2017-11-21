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
ms.openlocfilehash: d6e5ea4e5f8bae3fda190ac7a7136035aea0c948
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama
**ANSI 4.2** tarafından yazdırılan tanılama ve sonlandırma davranışını **assert** işlevi  
  
 **Assert** işlevi yazdırır bir tanılama iletisi ve çağrıları **abort** ifade yanlışsa yordamına (0). Tanılama iletisi şu formdadır:  
  
 **Onaylama işlemi başarısız**: *ifade***, dosya** *filename***, satır** *linenumber*  
  
 burada dosya adı kaynak dosyanın adıdır, satır numarası kaynak dosyada başarısız onayın satır sayısıdır. İfade doğru (sıfırdan farklı) ise hiçbir eylem gerçekleştirilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık işlevleri](../c-language/library-functions.md)