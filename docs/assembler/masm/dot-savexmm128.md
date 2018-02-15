---
title: .SAVEXMM128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e163f71b0c1d49f845cc871a26d4ee369843597
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="savexmm128"></a>.SAVEXMM128
Ya da oluşturur bir `UWOP_SAVE_XMM128` veya `UWOP_SAVE_XMM128_FAR` belirtilen XMM yazmaç için kod girdisi bırakma ve geçerli başlangıç sapmasını kullanarak uzaklığı. MASM en verimli kodlamayı seçecektir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>Açıklamalar  
 . SAVEXMM128 ml64.exe kullanıcıların nasıl çerçeve işlevi unwinds ve yalnızca gelen genişletir giriş içinde izin belirtmesine izin verir [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeleri kod oluşturmaz; yalnızca oluşturdukları `.xdata` ve `.pdata`. . SAVEXMM128 gerçekten unwound olmasını eylemlerini uygulamak yönergeleri ile gelmelidir. Bırakma yönergeleri ve bunlar makro bırakma sözleşmesi emin olmak için değiştirmemektir kodu sarmalamak için iyi bir uygulamadır.  
  
 `offset` 16'ın katları olmalıdır.  
  
 Daha fazla bilgi için bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)