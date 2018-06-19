---
title: NMAKE çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29516dcbcf650225ec3b86eee9e135a35bff82f4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379711"
---
# <a name="running-nmake"></a>NMAKE Çalıştırma
## <a name="syntax"></a>Sözdizimi  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca belirtilen NMAKE derlemeleri *hedefleri* veya ilk belirtilmemişse, makefile hedefleyin. İlk derleme görevleri dosyası hedefi olabilir bir [pseudotarget](../build/pseudotargets.md) diğer hedefleri oluşturur. NMAKE derleme görevleri dosyaları /F ile belirtilen kullanır; /F belirtilmezse, geçerli dizin derleme görevleri dosyasındaki kullanır. Hiçbir derleme görevleri dosyası belirtilirse, çıkarım kuralları komut satırı oluşturmak için kullandığı *hedefleri*.  
  
 `commandfile` Metin dosyası (veya yanıt dosyası) komut satırı giriş içerir. Diğer giriş önünde veya izleyin`commandfile`. Bir yola izin verilir. İçinde `commandfile`, satır sonları alanları olarak kabul edilir. Makro tanımları boşluk içeriyorsa tırnak işaretleri içine alın.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
 [NMAKE seçenekleri](../build/nmake-options.md)  
  
 [Tools.ini ve NMAKE](../build/tools-ini-and-nmake.md)  
  
 [NMAKE çıkış kodları](../build/exit-codes-from-nmake.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Başvurusu](../build/nmake-reference.md)