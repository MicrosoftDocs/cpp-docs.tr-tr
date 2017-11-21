---
title: "MASM Makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e42bbe4f724f711f407072c12a61ae9abbaca07d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="masm-macros"></a>MASM Makroları
Kullanımını kolaylaştırmak için [ham sözde işlemler](../build/raw-pseudo-operations.md), normal yordama öğesinin ve sonuçları oluşturmak için kullanılan ksamd64.inc içinde tanımlı makrolar kümesi vardır.  
  
## <a name="remarks"></a>Açıklamalar  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|alloc_stack(n)|Yığın çerçevesi (alt rsp, n kullanarak) n bayt ayırır ve yayar uygun geriye doğru izleme bilgilerini (.allocstack n)|  
|save_reg reg, loc|Kalıcı kayıt reg dosyasını RSP uzaklık konumu yığında kaydeder ve uygun bilgileri bırakma. (.savereg reg, loc)|  
|push_reg reg|Kalıcı kayıt reg yığına ve yayar uygun geriye doğru izleme bilgilerini. (.pushreg reg)|  
|rex_push_reg reg|2 bayt push kullanarak Yığında kalıcı kayıt kaydedin ve yayar uygun geriye doğru izleme bilgilerini bu kullanılmalıdır itme işlevi tamsayı olduğundan emin olmak için ilk yönerge işlevinde ise (.pushreg reg).|  
|save_xmm128 reg, loc|Yığında dosyasını RSP uzaklık konumu yığında reg XMM kaydının kaydeder ve uygun geriye doğru izleme bilgilerini (.savexmm128 reg, loc)|  
|set_frame reg, uzaklık|Çerçeve kayıt reg rsp + (mov ya da bir ö kullanarak) uzaklığı için ayarlar ve bilgiler (.set_frame reg, offset) uygun geriye doğru izleme|  
|push_eflags|Eflags pushfq yönergesiyle gönderir ve uygun geriye doğru izleme bilgilerini (gösterir.alloc_stack 8)|  
  
 Makrolar uygun kullanımıyla birlikte örnek işlev girişi şöyledir:  
  
```  
SkFrame struct   
Fill    dq ?; fill to 8 mod 16   
SavedRdi dq ?; saved register RDI   
SavedRsi dq ?; saved register RSI   
SkFrame ends  
  
sampleFrame struct  
Filldq?; fill to 8 mod 16  
SavedRdidq?; Saved Register RDI   
SavedRsi  dq?; Saved Register RSI  
sampleFrame ends  
  
sample2 PROC FRAME  
alloc_stack(sizeof sampleFrame)  
save_reg rdi, sampleFrame.SavedRdi  
save_reg rsi, sampleFrame.SavedRsi  
.end_prolog  
  
; function body  
  
mov rsi, sampleFrame.SavedRsi[rsp]  
mov rdi, sampleFrame.SavedRdi[rsp]  
  
; Here’s the official epilog  
  
add rsp, (sizeof sampleFrame)  
ret  
sample2 ENDP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MASM için Yardımcıları Bırakma](../build/unwind-helpers-for-masm.md)