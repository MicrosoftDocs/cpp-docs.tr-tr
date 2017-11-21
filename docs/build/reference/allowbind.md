---
title: -ALLOWBIND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /allowbind
dev_langs: C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e1a039a6f62a3cf2dd296677f81f672ab462f7b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="allowbind"></a>/ALLOWBIND
DLL bağlı olup olmadığını belirtir.  
  
```  
  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ALLOWBIND** seçeneği ayarlar biraz DLL üstbilgisinde Bind.exe için görüntüyü bağlanması için izin verildiğini gösterir. Bağlama yükleyicisi rebase ve her başvurulan DLL için adres düzeltmesi gerçekleştirmek sahip olmadığında daha hızlı yüklemek bir görüntü izin verebilirsiniz. Dijital olarak imzalı olup olmadığını bağlanması için bir DLL istemeyebilirsiniz — bağlama imza geçersiz kılar. Bağlama hiçbir etkisi adres boşluğu düzeni rastgele seçimini (ASLR) kullanarak görüntü için etkinse **/DYNAMICBASE** ASLR destekleyen Windows sürümleri üzerinde.  
  
 Kullanım **/ALLOWBIND:NO** DLL bağlamayı Bind.exe önlemek için.  
  
 Daha fazla bilgi için bkz: [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) bağlayıcı seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)