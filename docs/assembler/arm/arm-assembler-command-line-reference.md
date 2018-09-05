---
title: ARM Assembler komut satırı başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88f35035944ee24bed0bef8733db0e2c0139c83
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685347"
---
# <a name="arm-assembler-command-line-reference"></a>ARM Assembler Komut Satırı Başvurusu

Bu makalede Microsoft ARM assembler komut satırı bilgileri sağlayan *armasm*, ortak nesne dosyası biçimi (COFF), Microsoft uygulamasına ARMv7 Thumb derleme dili derler. Bağlayıcı, kitaplıkçı tarafından oluşturulan nesne kitaplıkları ile birlikte C derleyicisi veya ARM derleyicisi tarafından üretilen nesne kodu COFF koduyla bağlayabilirsiniz.

## <a name="syntax"></a>Sözdizimi

> **armasm** [*seçenekleri*] *kaynakdosya* *objectfile*
> **armasm** [*seçenekleri *] **-o** *objectfile* *kaynakdosya*

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
Sıfır veya daha fazlasını birleşimi:

- **-hataları** *dosya adı*<br/>
   Hata ve uyarı iletilerini yönlendirmek *filename*.

- **-i** *dir*[**;** <em>dir</em>]<br/>
   Belirtilen dizinlerde arama yoluna ekleyin.

- **-önceden** *yönergesi*<br/>
   Bir sembol ön tanımlamasında SETA, SETL veya KÜMELERİ yönergesi belirtin.<br/>
   Örnek: **armasm.exe-"SETA 150 Say" source.asm ön tanımlamasında**<br/>
   Daha fazla bilgi için [ARM derleyici armasm Başvuru Kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html).

- **-nowarn**<br/>
   Tüm uyarı iletilerini devre dışı bırakın.

- **-Yoksay** *Uyarısı*<br/>
   Belirtilen uyarı devre dışı bırakın. Olası değerler için uyarılar hakkındaki bölüme bakın.

- **-Yardım**<br/>
   Komut satırı yardım iletisini yazdır.

- **-Makine** *makine*<br/>
   PE üstbilgisinde ayarlamak için makine türü belirtin.  Olası değerler için *makine* şunlardır:<br/>
   **ARM**— IMAGE_FILE_MACHINE_ARMNT için makine türünü ayarlar. Bu varsayılandır.<br/>
   **THUMB**— IMAGE_FILE_MACHINE_THUMB için makine türünü ayarlar.

- **-oldit**<br/>
   ARMv7 stili oluşturmak BT engeller.  Varsayılan olarak, ARMv8 uyumlu BT blokları oluşturulur.

- **-aracılığıyla** *dosya adı*<br/>
   Ek komut satırı bağımsız değişkenlerini okuma *filename*.

- **-16**<br/>
   Kaynak 16-bit Thumb yönergeleri birleştirin.  Bu varsayılandır.

- **-32**<br/>
   Kaynak 32 bit ARM yönergeleri birleştirin.

- **-g**<br/>
   Hata ayıklama bilgisi üretir.

- **-errorReport:** *seçeneği*<br/>
   Nasıl iç derleyici hatalarını Microsoft'a belirtin.  Olası değerler için *seçeneği* şunlardır:<br/>
   **Hiçbiri**— raporları gönderme.<br/>
   **İstemi**— raporları hemen göndermek için kullanıcıya sor.<br/>
   **Kuyruk**-sonraki yönetici oturum açma raporları göndermek için kullanıcıya sor. Bu varsayılandır.<br/>
   **Gönderme**— raporları otomatik olarak gönder.

*kaynakdosya*<br/>
Kaynak dosyanın adı.

*objectfile*<br/>
Nesne (çıkış) dosyasının adı.

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, tipik bir senaryoda armasm kullanmayı gösterir. İlk olarak, bir nesne (.obj) dosyası için bir derleme dili (.asm) kaynak dosyası oluşturmak için armasm kullanın. Ardından, CL komut satırı C derleyicisi (.c) kaynak dosyasını derlemek için kullanın ve ayrıca ARM nesne dosyası bağlamak için bağlayıcı seçeneği belirtin.

**armasm myasmcode.asm -o myasmcode.obj**

**cl myccode.c/Link myasmcode.obj**

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler Tanılama İletileri](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
[ARM Assembler Yönergeleri](../../assembler/arm/arm-assembler-directives.md)<br/>
