---
title: -ALLOWBIND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af4a9f3d898d0087f0e8e861ccfe72e4adadb1de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)