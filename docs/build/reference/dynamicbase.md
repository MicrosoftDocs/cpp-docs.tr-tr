---
title: -DYNAMICBASE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d7a4cf7aa35d7ad6b41fc6d61f3f27662ae2c8d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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