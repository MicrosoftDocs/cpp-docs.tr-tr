---
title: Assert işlevinin yazdırdığı tanılama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c219669d018dc8c4cb038e90dffd1137877f422
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382883"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama
**ANSI 4.2** tarafından yazdırılan tanılama ve sonlandırma davranışını **assert** işlevi  
  
 **Assert** işlevi yazdırır bir tanılama iletisi ve çağrıları **abort** ifade yanlışsa yordamına (0). Tanılama iletisi şu formdadır:  
  
 **Onaylama işlemi başarısız**: *ifade ***, dosya** *filename ***, satır** *linenumber*  
  
 burada dosya adı kaynak dosyanın adıdır, satır numarası kaynak dosyada başarısız onayın satır sayısıdır. İfade doğru (sıfırdan farklı) ise hiçbir eylem gerçekleştirilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık İşlevleri](../c-language/library-functions.md)