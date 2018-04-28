---
title: ARM Assembler tanılama iletileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1616b4bd9c4b64e771ec537a1b8cd7b582702222
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM Assembler Tanılama İletileri
Microsoft ARM assembler (*armasm*) bunları karşılaştığında tanılama uyarıları ve hataları yayar. Bu makalede, en sık karşılaşılan iletileri açıklanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## <a name="diagnostic-messages"></a>Tanılama iletileri  
  
### <a name="errors"></a>Hatalar  
 A2193: Bu yönergeyi beklenmeyen davranışlara oluşturur.  
 ARM mimarisi, bu yönergeyi çalıştırıldığında ne olacağını garanti edemez.  Bu yönerge, iyi tanımlanmış formları hakkında daha fazla ayrıntı için inceleyin [ARM mimarisi referans el ile](http://go.microsoft.com/fwlink/p/?linkid=246464).  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196: 16 bit yönerge kodlanamıyor  
 Bir 16 bit Flash yönergesi belirtilen yönerge kodlanamıyor.  Bir 32 bit yönergesi belirtin veya hedef etiketi bir 16 bit yönergesi aralığına getirmek için kodu yeniden düzenleyin.  
  
 Bir 32 bit dalı encodable olsa bile assembler 16 bit dalında kodlamak ve bu hata ile başarısız deneyebilir. Kullanarak bu sorunu çözebilir `.W` açıkça dal 32-bit olarak işaretlemek için tanımlayıcısı.  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 A2202: Flash bölgede izin verilmiyor öncesi UAL yönergesi sözdizimi  
 Flash kod birleşik Assembler dili (UAL) sözdizimini kullanmanız gerekir.  Eski sözdizimi artık kabul edilir  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513: Döndürme bile olmalıdır  
 ARM modunda sabitleri belirtmek için alternatif bir söz dizimi yoktur.  Yazma yerine `#<const>`, yazabileceğiniz `#<byte>,#<rot>`, değer döndürerek elde sabit değeri temsil eden `<byte>` sağ tarafından `<rot>`.  Bu sözdizimini kullandığınızda, değerini olmalısınız `<rot>` bile.  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557: Yanlış geri yazılacak bayt sayısı  
 NEON yapısı yük ve yönergeleri depolamak (`VLDn`, `VSTn`), temel kayıt için geri yazma belirtmek için alternatif bir söz dizimi yoktur.  Ünlem işareti (!) sonra adresi yerine koyma, temel bir kasaya eklenecek uzaklığı gösterir hemen bir değer belirtebilirsiniz.  Bu söz dizimini kullanıyorsanız, tam yüklenen ya da yönergesi tarafından depolanan bayt sayısı belirtmelisiniz.  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### <a name="warnings"></a>Uyarılar  
 A4228: Hizalama değeri alanı hizalama aşıyor; yıkıcıları hizalama  
 Belirtilen hizalama bir `ALIGN` yönergesi kapsayan hizalama büyük `AREA`.  Derleyici, sonuç olarak, garanti edemez `ALIGN` yönergesi kullanılacaktır.  
  
 Bu sorunu gidermek için belirtebilirsiniz `AREA` yönergesi bir `ALIGN` eşit veya bundan büyük istenen hizalama özniteliği.  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508: Bu döndürülmüş sabiti kullanımını kullanım dışıdır  
 ARM modunda sabitleri belirtmek için alternatif bir söz dizimi yoktur.  Yazma yerine `#<const>`, yazabileceğiniz `#<byte>,#<rot>`, değer döndürerek elde sabit değeri temsil eden `<byte>` sağ tarafından `<rot>`.  Bazı bağlamlarda ARM Bu döndürülmüş sabitleri kullanımını kullanım dışı. Bu durumlarda, basic kullanan `#<const>` sözdizimi yerine.  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509: Bu form koşullu yönergenin kullanım dışıdır  
 Bu form koşullu yönergenin ARMv8 mimarisinde ARM tarafından kullanım dışıdır. Koşullu dal kullanılacak kodunu değiştirmenizi öneririz. Hangi koşullu yönergeleri hala desteklenmektedir görmek için başvurun [ARM mimarisi referans el ile](http://go.microsoft.com/fwlink/p/?linkid=246464).  
  
 Bu uyarı değil ne zaman gösterilen `-oldit` komut satırı anahtarı kullanılır.  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ARM Assembler komut satırı başvurusu](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Yönergeleri](../../assembler/arm/arm-assembler-directives.md)