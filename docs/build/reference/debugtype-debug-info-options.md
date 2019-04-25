---
title: /DEBUGTYPE (Hata Ayıklama Bilgisi Seçenekleri)
ms.date: 11/04/2016
f1_keywords:
- /debugtype
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
ms.openlocfilehash: 00e3cb61f8ec9aa707bb72aa9ff05a64f98d4e47
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272301"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (Hata Ayıklama Bilgisi Seçenekleri)

/DEBUGTYPE seçeneği/Debug seçeneği tarafından oluşturulan hata ayıklama bilgileri türlerini belirtir.

```
/DEBUGTYPE:[CV | PDATA | FIXUP]
```

## <a name="arguments"></a>Arguments

**CV**<br/>
Simgeler, satır numaraları ve diğer nesne derleme bilgileri PDB dosyası için hata ayıklama bilgileri yayılamıyor söyler. Varsayılan olarak, bu seçenek etkin olduğunda **/DEBUG** belirtilir ve **/DEBUGTYPE** belirtilmedi.

**PDATA**<br/>
.Pdata ve .xdata giriş PDB dosyası hata ayıklama akış bilgilerini eklemek için söyler. Varsayılan olarak, bu seçenek etkin olduğunda hem **/DEBUG** ve **Driver/Driver** seçenekler belirtilir. Varsa **/DEBUGTYPE:PDATA** belirtilen kendisi tarafından bağlayıcı otomatik olarak içerir PDB dosyasında hata ayıklama. Varsa **/DEBUGTYPE:PDATA, düzeltme** belirtildiğinde, bağlayıcı PDB dosyasında hata ayıklama içermez.

**DÜZELTME**<br/>
PDB dosyası hata ayıklama akış bilgilerini konum değiştirme tablosu girdileri eklemek için söyler. Varsayılan olarak, bu seçenek etkin olduğunda hem **/DEBUG** ve **/PROFILE** seçenekler belirtilir. Varsa **/DEBUGTYPE:FIXUP** veya **/DEBUGTYPE:FIXUP, PDATA** belirtildiğinde, bağlayıcı PDB dosyasında hata ayıklama içermez.

Bağımsız değişkenleri **/DEBUGTYPE** herhangi bir sırada virgül ile ayırarak birleştirilebilir. **/DEBUGTYPE** seçenek ve bağımsız değişkenlerinden büyük küçük harfe duyarlı değildir.

## <a name="remarks"></a>Açıklamalar

Kullanım **/DEBUGTYPE** konum değiştirme tablosu veri veya .pdata ve .xdata başlık bilgilerini dahil edilmesi hata ayıklama akışında belirtmek için seçeneği. Bu, çekirdek modu kodu bozucu bir çekirdek hata ayıklayıcısı içinde görülebilir kullanıcı modu kodu hakkında bilgi dahil etmesini bağlayıcıya neden olur. Hata ayıklama simgeleri ne zaman kullanılabilir hale getirmek **düzeltme** olduğundan belirtilen dahil **CV** bağımsız değişken.

Uygulamalar için tipik olan kullanıcı modu kodunda hata ayıklamak için **/DEBUGTYPE** seçeneği gerekli olmayan. Varsayılan olarak, hata ayıklama belirten derleyici anahtarları çıktı ([/z7, / zi, /zı](z7-zi-zi-debug-information-format.md)) tüm bilgileri Visual Studio hata ayıklayıcı gösterin. Kullanım **/DEBUGTYPE:PDATA** veya **/DEBUGTYPE:CV, PDATA, düzeltme** bir aygıt sürücüsü için bir yapılandırma uygulaması gibi kullanıcı modu hem de çekirdek modu bileşenlerini bir araya getiren kod hatalarını ayıklamak için. Çekirdek modu hata ayıklayıcıları hakkında daha fazla bilgi için bkz: [hata ayıklama araçları için Windows (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)

## <a name="see-also"></a>Ayrıca bkz.

[/DEBUG (Hata Ayıklama Bilgileri Üret)](debug-generate-debug-info.md)<br/>
[/DRIVER (Windows NT Çekirdek Modu Sürücüsü)](driver-windows-nt-kernel-mode-driver.md)<br/>
[/PROFILE (Performans Araçları Profil Oluşturucusu)](profile-performance-tools-profiler.md)<br/>
[(WinDbg, KD, CDB, NTSD) Windows için hata ayıklama araçları](/windows-hardware/drivers/debugger/index)
