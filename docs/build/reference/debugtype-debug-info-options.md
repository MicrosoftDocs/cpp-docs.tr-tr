---
description: Şu konuda daha fazla bilgi edinin:/DEBUGTYPE (hata ayıklama bilgisi seçenekleri)
title: /DEBUGTYPE (Hata Ayıklama Bilgisi Seçenekleri)
ms.date: 11/04/2016
f1_keywords:
- /debugtype
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
ms.openlocfilehash: 858d5ed8eb449931229700a10b755dd61ef371cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201735"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (Hata Ayıklama Bilgisi Seçenekleri)

/DEBUGTYPE seçeneği,/DEBUG seçeneği tarafından oluşturulan hata ayıklama bilgilerinin türlerini belirtir.

```
/DEBUGTYPE:[CV | PDATA | FIXUP]
```

## <a name="arguments"></a>Arguments

**CV**<br/>
Bağlayıcının simgelere, satır numaralarına ve diğer nesne derleme bilgilerine ilişkin hata ayıklama bilgilerini PDB dosyasında yaymasını söyler. Varsayılan olarak, **/Debug** belirtildiğinde ve **/DEBUGTYPE** belirtilmediğinde bu seçenek etkin olur.

**PDATA**<br/>
Bağlayıcının PDB dosyasındaki hata ayıklama akışı bilgilerine. pdata ve. xdata girdileri eklemesini söyler. Varsayılan olarak, bu seçenek **/Debug** ve **/Driver** seçenekleri belirtildiğinde etkindir. **/DEBUGTYPE: PDATA** kendi kendine belirtilmişse, bağlayıcı OTOMATIK olarak PDB dosyasındaki hata ayıklama sembollerini içerir. **/DEBUGTYPE: PDATA, FIXUP** belirtilmişse, bağlayıcı PDB dosyasındaki hata ayıklama sembollerini içermez.

**AYARLAMA**<br/>
Bağlayıcının PDB dosyasındaki hata ayıklama akışı bilgilerine konum değiştirme tablosu girişleri eklemesini söyler. Varsayılan olarak, bu seçenek **/Debug** ve **/profile** seçeneklerinin her ikisi de belirtildiğinde etkindir. **/DEBUGTYPE: Fixup** veya **/DEBUGTYPE: FIXUP, PDATA** belirtilmişse, bağlayıcı PDB dosyasındaki hata ayıklama sembollerini içermez.

**/DEBUGTYPE** bağımsız değişkenleri, virgülle ayırarak herhangi bir sırada birleştirilebilir. **/DEBUGTYPE** seçeneği ve bağımsız değişkenleri büyük/küçük harfe duyarlı değildir.

## <a name="remarks"></a>Açıklamalar

Hata ayıklama akışında yer değiştirme tablosu verilerinin veya. pdata ve. xdata üst bilgi bilgilerinin dahil edilmesini belirtmek için **/DEBUGTYPE** seçeneğini kullanın. Bu, bağlayıcının çekirdek modu kodunda kırılmaya karşı bir çekirdek hata ayıklayıcısında görünen Kullanıcı modu kodu hakkında bilgi içermesini sağlar. **Düzeltme** belirtildiğinde hata ayıklama sembollerini kullanılabilir hale getirmek için **CV** bağımsız değişkenini ekleyin.

Uygulamalar için tipik olan kullanıcı modundaki kodun hatalarını ayıklamak için, **/DEBUGTYPE** seçeneği gerekli değildir. Varsayılan olarak, hata ayıklama çıkışını belirten derleyici anahtarları ([/Z7,/Zi,/Zi](z7-zi-zi-debug-information-format.md)), Visual Studio hata ayıklayıcısı için gereken tüm bilgileri yayar. Bir cihaz sürücüsü yapılandırma uygulaması gibi Kullanıcı modu ve çekirdek modu bileşenlerini birleştiren kodda hata ayıklamak için **/DEBUGTYPE: PDATA** veya **/DEBUGTYPE: CV, PDATA, FIXUP** komutunu kullanın. Çekirdek modu hata ayıklayıcıları hakkında daha fazla bilgi için bkz. [Windows Için hata ayıklama araçları (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)

## <a name="see-also"></a>Ayrıca bkz.

[/DEBUG (hata ayıklama bilgisi oluştur)](debug-generate-debug-info.md)<br/>
[/DRıVER (Windows NT Çekirdek modu sürücüsü)](driver-windows-nt-kernel-mode-driver.md)<br/>
[/PROFILE (performans araçları Profil Oluşturucusu)](profile-performance-tools-profiler.md)<br/>
[Windows için hata ayıklama araçları (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)
