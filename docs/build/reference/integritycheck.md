---
title: -INTEGRITYCHECK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /INTEGRITYCHECK
dev_langs: C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.assetid: 2a293705-4396-421b-a5a5-693b4b867a85
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20fa72f8cc2d12c719f0e50c250052a191b5ee81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="integritycheck"></a>/INTEGRITYCHECK
İkili görüntü dijital imzasını yükleme zamanında denetlenmesi gerektiğini belirtir.  
  
```  
  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 DLL dosyası veya yürütülebilir dosya üstbilgisinde, bu seçenek Windows görüntüsünü yüklemek için bellek yöneticisi tarafından bir dijital imza denetimi gerektirir bir bayrak ayarlar. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yok sayar. Bu seçenek, çekirdek modu kodu uygulamak ve tüm aygıt sürücülerini önerilen 64-bit DLL'ler için ayarlamanız gerekir. Daha fazla bilgi için bkz: [çekirdek modu kod imzalama izlenecek](http://go.microsoft.com/fwlink/?linkid=237093) MSDN Web sitesinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)