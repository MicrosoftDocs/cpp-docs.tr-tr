---
title: Ham sözde işlemler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff3b9dd065b4bf1f64950f97237dec08b10d23cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369935"
---
# <a name="raw-pseudo-operations"></a>Ham Sözde İşlemler
Bu konuda sözde işlemler listelenmiştir.  
  
## <a name="remarks"></a>Açıklamalar  
  
|Sahte işlemi|Açıklama|  
|----------------------|-----------------|  
|PROC çerçeve [: ehandler]|Nedenler işlevi oluşturmak için MASM tablo girdisi pdata'da ve geriye doğru izleme bilgilerini xdata'daki bir işlevin yapılandırılmış özel durum işleme bırakma davranışı.  Ehandler varsa bu proc xdata'daki dile özel işleyici olarak girilir.<br /><br /> Çerçeve özniteliği kullanıldığında, onu gelmelidir bir. ENDPROLOG yönergesi.  İşlev yaprak işlevi ise (tanımlandığı gibi [işlev türleri](../build/function-types.md)) bu sözde işlemler geri kalanı gibi FRAME özniteliği de gereksizdir.|  
|. PUSHREG yazmaç|Başlangıç uzaklığı geçerli kullanarak belirtilen yazmaç sayısı için UWOP_PUSH_NONVOL bırakma kod girdisi oluşturur.<br /><br /> Bu, yalnızca kalıcı tamsayı yazmaçları ile kullanılmalıdır.  İçin gönderim volatile yazmaçların kullanmak bir. ALLOCSTACK 8'de, bunun yerine|  
|. SETFRAME yazmaç, uzaklığı|Çerçeve doldurur alan ve uzaklık bırakma bilgilerin uzaklık ve belirtilen yazmaç kullanarak kaydedin. Uzaklık 16 katları olmalıdır ve 240 küçük veya buna eşit. Bu yönerge, aynı zamanda geçerli başlangıç sapmasını kullanarak belirtilen yazmaç için UWOP_SET_FPREG bırakma kod girdisi oluşturur.|  
|. ALLOCSTACK boyut|UWOP_ALLOC_SMALL veya geçerli sapma için belirtilen boyut UWOP_ALLOC_LARGE oluşturur.<br /><br /> Boyut işleneni 8 katı olmalıdır.|  
|. SAVEREG yazmaç, uzaklığı|UWOP_SAVE_NONVOL veya belirtilen YAZMAÇ ve geçerli başlangıç sapmasını kullanarak için UWOP_SAVE_NONVOL_FAR bırakma kod girdisi oluşturur. MASM en verimli kodlamayı seçecektir.<br /><br /> Uzaklık, pozitif ve 8 katları olması gerekir.  Uzaklığı genellikle RSP içinde olduğundan, yordam çerçevesinin temel göreli veya ölçeklendirilmemiş çerçeve işaretçisi bir çerçeve işaretçisi kullanıyorsanız.|  
|. SAVEXMM128 yazmaç, uzaklığı|UWOP_SAVE_XMM128 veya belirtilen XMM YAZMAÇ ve geçerli başlangıç sapmasını kullanarak UWOP_SAVE_XMM128_FAR bırakma kod girdisi oluşturur. MASM en verimli kodlamayı seçecektir.<br /><br /> Uzaklık, pozitif ve 16 katları olması gerekir.  Uzaklığı genellikle RSP içinde olduğundan, yordam çerçevesinin temel göreli veya ölçeklendirilmemiş çerçeve işaretçisi bir çerçeve işaretçisi kullanıyorsanız.|  
|. PUSHFRAME [kod]|UWOP_PUSH_MACHFRAME bırakma kod girdisi oluşturur. İsteğe bağlı kod belirtilirse, bırakma kod girdisi 1 değiştiricisi verilir. Aksi takdirde değiştirici 0'dır.|  
|.ENDPROLOG|Giriş bildirimlerinin sonuna işaret eder.  İlk 255 bayt işlevinin bulunması gerekir.|  
  
 Bir örnek işlevi giriş çoğu işlem için doğru kullanımı şöyledir:  
  
```  
sample PROC FRAME     
   db      048h; emit a REX prefix, to enable hot-patching  
push rbp  
.pushreg rbp  
sub rsp, 040h  
.allocstack 040h     
lea rbp, [rsp+020h]  
.setframe rbp, 020h  
movdqa [rbp], xmm7  
.savexmm128 xmm7, 020h;the offset is from the base of the frame  
;not the scaled offset of the frame  
mov [rbp+018h], rsi  
.savereg rsi, 038h  
mov [rsp+010h], rdi  
.savereg rdi, 010h; you can still use RSP as the base of the frame  
; or any other register you choose  
.endprolog  
  
; you can modify the stack pointer outside of the prologue (similar to alloca)  
; because we have a frame pointer.  
; if we didn’t have a frame pointer, this would be illegal  
; if we didn’t make this modification,  
; there would be no need for a frame pointer  
  
sub rsp, 060h  
  
; we can unwind from the following AV because of the frame pointer  
  
mov rax, 0  
mov rax, [rax] ; AV!  
  
; restore the registers that weren’t saved with a push  
; this isn’t part of the official epilog, as described in section 2.5  
  
movdqa xmm7, [rbp]  
mov rsi, [rbp+018h]  
mov rdi, [rbp-010h]  
  
; Here’s the official epilog  
  
lea rsp, [rbp-020h]  
pop rbp  
ret  
sample ENDP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MASM için Yardımcıları Bırakma](../build/unwind-helpers-for-masm.md)