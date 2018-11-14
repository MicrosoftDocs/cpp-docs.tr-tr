---
title: MASM Makroları
ms.date: 11/04/2016
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
ms.openlocfilehash: 8a00852a3a763aae5fda34d7e0fde664997a0bdb
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328831"
---
# <a name="masm-macros"></a>MASM Makroları

Kullanımını kolaylaştırmak için [ham sözde işlemler](../build/raw-pseudo-operations.md), tipik yordamı öğesinin ve sonuçları oluşturmak için kullanılan ksamd64.inc içinde tanımlı makrolar, bir dizi vardır.

## <a name="remarks"></a>Açıklamalar

|Makrosu|Açıklama|
|-----------|-----------------|
|alloc_stack(n)|Bir yığın çerçevesi (kullanarak alt rsp, n) n bayt ayırır ve yayan uygun geriye doğru izleme bilgilerini (.allocstack n)|
|save_reg reg, loc|Yığında dosyasını RSP uzaklık konumu kalıcı kayıt reg kaydeder ve uygun geriye doğru izleme bilgilerini. (.savereg reg, loc)|
|push_reg reg|Kalıcı kayıt reg yığına ve yayan uygun geriye doğru izleme bilgilerini. (.pushreg reg)|
|rex_push_reg reg|2 bayt push kullanarak yığında bir kayıt kaydedin uygun geriye doğru izleme bilgilerini bu kullanılmalıdır anında iletme işlevi anında düzeltme eki eklenebilen olduğundan emin olmak için ilk yönerge işlevindeki ise (.pushreg reg).|
|save_xmm128 reg, loc|Yığında dosyasını RSP uzaklık konumu reg XMM kaydının kaydeder ve uygun geriye doğru izleme bilgilerini (.savexmm128 reg, loc)|
|set_frame reg, uzaklık|Çerçeve kaydı reg rsp + (mov ya da bir ö kullanarak) uzaklığı için ayarlar ve uygun geriye doğru izleme bilgilerini (.set_frame reg, uzaklık)|
|push_eflags|Pushfq yönergesiyle eflags ve bilgilerini (gösterir 8 .alloc_stack) uygun geriye doğru izleme|

Örnek işlevi giriş makroları uygun kullanımıyla birlikte aşağıda verilmiştir:

```asm
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