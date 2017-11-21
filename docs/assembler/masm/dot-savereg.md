---
title: . SAVEREG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAVEREG
dev_langs: C++
helpviewer_keywords: .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e55abe8a5661184b022fad3f6a50dc9813cae9d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="savereg"></a>.SAVEREG
Ya da oluşturur bir `UWOP_SAVE_NONVOL` veya `UWOP_SAVE_NONVOL_FAR` belirtilen yazmaç için kod girdisi bırakma (`reg`) ve uzaklık (`offset`) geçerli başlangıç sapmasını kullanarak. MASM en verimli kodlamayı seçecektir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.SAVEREG reg, offset  
```  
  
## <a name="remarks"></a>Açıklamalar  
 . SAVEREG ml64.exe kullanıcıların nasıl çerçeve işlevi unwinds belirtmesine izin verir ve yalnızca gelen genişletir giriş içinde izin [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeleri kod oluşturmaz; yalnızca oluşturdukları `.xdata` ve `.pdata`. . SAVEREG gerçekten unwound olmasını eylemlerini uygulamak yönergeleri ile gelmelidir. Bırakma yönergeleri ve bunlar makro bırakma sözleşmesi emin olmak için değiştirmemektir kodu sarmalamak için iyi bir uygulamadır.  
  
 Daha fazla bilgi için bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)