---
title: . PUSHFRAME | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .PUSHFRAME
dev_langs:
- C++
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fa9b03f1075418019f41f3d537607372bf8d498
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="pushframe"></a>.PUSHFRAME
Oluşturan bir `UWOP_PUSH_MACHFRAME` kod girişi bırakma. Varsa isteğe bağlı `code` belirtilirse, bırakma kod girdisi olarak 1 değiştiricisi verilir. Aksi takdirde değiştirici 0'dır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.PUSHFRAME [code]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 . PUSHFRAME ml64.exe kullanıcıların nasıl çerçeve işlevi unwinds belirtmesine izin verir ve yalnızca gelen genişletir giriş içinde izin [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeleri kod oluşturmaz; yalnızca oluşturdukları `.xdata` ve `.pdata`. . PUSHFRAME gerçekten unwound olmasını eylemlerini uygulamak yönergeleri ile gelmelidir. Bırakma yönergeleri ve bunlar makro bırakma sözleşmesi emin olmak için değiştirmemektir kodu sarmalamak için iyi bir uygulamadır.  
  
 Daha fazla bilgi için bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)