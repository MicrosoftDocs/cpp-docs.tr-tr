---
title: Ham Sözde İşlemler
ms.date: 11/04/2016
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
ms.openlocfilehash: 04dfe4d59c05dfcf22d0e64063fbc4953cbcb2f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538040"
---
# <a name="raw-pseudo-operations"></a>Ham Sözde İşlemler

Bu konuda, sözde işlemler listelenmiştir.

## <a name="remarks"></a>Açıklamalar

|Sahte işlem|Açıklama|
|----------------------|-----------------|
|PROC çerçeve [: ehandler]|Neden bir işlev oluşturmak için MASM tablo .pdata girişi ve geriye doğru izleme bilgilerini sanal işlem bulunur, bir işlevin yapılandırılmış özel durum işleme geriye doğru davranışı.  Bu yordam ehandler varsa sanal işlem içinde bulunur dile özel işleyici girilir.<br /><br /> Çerçeve öznitelik kullanıldığında, gelmelidir bir. ENDPROLOG yönergesi.  İşlev bir yaprak işlevi ise (sınıfında tanımlandığı gibi [işlev türleri](../build/function-types.md)) bu sözde işlemler geri kalanında olduğu gibi KARE öznitelik gereksizdir.|
|. PUSHREG yazmaç|Bir giriş geçerli kullanarak belirtilen kayıt numarası için UWOP_PUSH_NONVOL geriye doğru izleme kodu girişi oluşturur.<br /><br /> Bu, yalnızca kalıcı tamsayı yazmaçları ile kullanılmalıdır.  Volatile yazmaçların bildirimler için kullanın. bir. ALLOCSTACK 8'de, bunun yerine|
|. SETFRAME yazmaç, offset|Çerçeve doldurur, alan ve uzaklık uzaklığı ve belirtilen kaydı kullanarak geriye doğru izleme bilgileri kaydedin. Uzaklık 16 olmalıdır ve 240 küçüktür veya eşittir. Bu yönerge ayrıca UWOP_SET_FPREG bırakma kod girdisi geçerli başlangıç uzaklığını kullanarak belirtilen kayıt oluşturur.|
|. ALLOCSTACK boyutu|UWOP_ALLOC_SMALL veya geçerli uzaklık için belirtilen boyut UWOP_ALLOC_LARGE oluşturur.<br /><br /> İşlenen boyutu 8'in katı olmalıdır.|
|. SAVEREG yazmaç, offset|UWOP_SAVE_NONVOL ya da belirtilen ve geçerli prolog sapmasını kullanarak UWOP_SAVE_NONVOL_FAR geriye doğru izleme kod girişini oluşturur. MASM en verimli kodlama seçersiniz.<br /><br /> Uzaklık, pozitif ve 8'in katı olmalıdır.  Uzaklığı olan genellikle RSP içinde olan, yordam çerçevesinin tabanı göre veya bir çerçeve işaretçisi ölçeklendirilmemiş çerçeve işaretçisini kullanıyorsanız.|
|. SAVEXMM128 yazmaç, offset|UWOP_SAVE_XMM128 ya da belirtilen XMM kaydı ve geçerli prolog sapmasını kullanarak UWOP_SAVE_XMM128_FAR geriye doğru izleme kod girişini oluşturur. MASM en verimli kodlama seçersiniz.<br /><br /> Uzaklık, pozitif ve 16 katı olmalıdır.  Uzaklığı olan genellikle RSP içinde olan, yordam çerçevesinin tabanı göre veya bir çerçeve işaretçisi ölçeklendirilmemiş çerçeve işaretçisini kullanıyorsanız.|
|. PUSHFRAME [kod]|UWOP_PUSH_MACHFRAME geriye doğru izleme kodu girişi oluşturur. İsteğe bağlı kod belirtilmezse, geriye doğru izleme kodu giriş 1 değiştiricisi verilir. Aksi takdirde değiştirici 0'dır.|
|.ENDPROLOG|Giriş bildirimlerinin sonuna işaret eder.  İşlevin ilk 255 bayt cinsinden olmalıdır.|

İşlem, en uygun kullanım ile örnek işlev girişi şu şekildedir:

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