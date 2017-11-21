---
title: "ARM Assembler komut satırı başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bb9bbdd6deb0a8e459f2f2b8d5b6188c7517e6c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="arm-assembler-command-line-reference"></a>ARM Assembler Komut Satırı Başvurusu
Bu makalede Microsoft ARM assembler komut satırı bilgilerini sağlar *armasm*, ortak nesne dosyası biçimi (COFF), Microsoft uygulamasına ARMv7 Flash assembly dili derler. Bağlayıcı COFF kodu ARM assembler veya kitaplığı tarafından oluşturulan nesne kitaplıkları ile birlikte C Derleyici tarafından üretilen nesne kodu ile bağlayabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### <a name="parameters"></a>Parametreler  
 `options`  
 -hataları`filename`  
 Hata ve uyarı iletileri yönlendirmek `filename`.  
  
 -i`dir[;dir]`  
 Belirtilen dizin INCLUDE arama yoluna ekleyin.  
  
 -önceden`directive`  
 Bir simge önceden tanımlamayı SETA, SETL veya KÜMELERİ yönergesi belirtin. Örnek: **armasm.exe-"SETA 150 COUNT" source.asm önceden**. Daha fazla bilgi için bkz: [ARM assembler araçları Kılavuzu](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 -nowarn  
 Tüm uyarı iletilerini devre dışı bırakın.  
  
 -Yoksay`warning`  
 Belirtilen uyarı devre dışı bırakın. Olası değerler için uyarılar hakkındaki bölüme bakın.  
  
 -Yardım  
 Komut satırı Yardım iletisi yazdırın.  
  
 -Makine`machine`  
 PE üstbilgisinde ayarlanan için makine türünü belirtin.  Olası değerler için `machine` şunlardır:  
**ARM**— IMAGE_FILE_MACHINE_ARMNT için makine türünü ayarlar. Bu varsayılandır.   
**Flash**— IMAGE_FILE_MACHINE_THUMB için makine türünü ayarlar.  
  
 -oldit  
 ARMv7 Stil Oluştur BT engeller.  Varsayılan olarak, ARMv8 uyumlu BT blokları oluşturulur.  
  
 -aracılığıyla`filename`  
 Ek komut satırı bağımsız değişkenlerini okuma `filename`.  
  
 -16  
 Kaynak 16 bit Flash yönergeleri birleştirin.  Bu varsayılandır.  
  
 -32  
 Kaynak 32-bit ARM yönergeleri birleştirin.  
  
 -g  
 Hata ayıklama bilgisi oluşturur.  
  
 -errorReport:`option`  
 Hataları Microsoft'a bildirilir nasıl iç derleyici belirtin.  Olası değerler için `option` şunlardır:   
**Hiçbiri**— raporları gönderme.   
**İstemi**— raporları hemen göndermek için kullanıcıya sor.   
**sıra**— sonraki yönetici oturum açma sırasında raporları göndermek için kullanıcıya sor. Bu varsayılandır.   
**Gönderme**— raporları otomatik olarak gönder.  
  
 `sourcefile`  
 Kaynak dosyanın adı.  
  
 `objectfile`  
 Nesne (çıktı) dosyasının adı.  
  
 Aşağıdaki örnek, tipik bir senaryoda armasm kullanımı gösterilmiştir. İlk olarak, bir nesne (.obj) dosyası bir derleme dili kaynak (.asm) dosyasını oluşturmak için armasm kullanın. Ardından, CL komut satırı C Derleyici bir kaynak (.c) dosyası derlemek için kullanın ve ayrıca ARM nesne dosyası bağlamak için bağlayıcı seçeneği belirtin.  
  
 **armasm myasmcode.asm -o myasmcode.obj**  
  
 **cl myccode.c/Link myasmcode.obj**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ARM Assembler tanılama iletileri](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM Assembler yönergeleri](../../assembler/arm/arm-assembler-directives.md)