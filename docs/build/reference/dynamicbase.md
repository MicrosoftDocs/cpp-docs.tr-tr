---
title: -DYNAMICBASE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /dynamicbase
dev_langs: C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b5af34353db3c5b7cebaf02e8ce6b1bd9518cc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dynamicbase"></a>/DYNAMICBASE
Yürütülebilir bir görüntü rastgele yükleme zamanında adres boşluğu düzeni rastgele seçimini (ASLR) kullanarak rebased olup olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bağlayıcı ayarlar **/DYNAMICBASE** seçeneği.  
  
 Bu seçenek yükleyicisi rastgele görüntü yükleme zamanında rebase olup olmadığını belirtmek için yürütülebilir görüntü üstbilgisinin değiştirir.  
  
 ASLR, Windows Vista, Windows Server 2008, Windows 7, Windows 8 ve Windows Server 2012 desteklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)   
 [Windows ISV yazılım güvenlik Savunmaları](http://msdn.microsoft.com/library/bb430720.aspx)