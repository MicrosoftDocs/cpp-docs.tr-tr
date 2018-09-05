---
title: -DEBUGTYPE (hata ayıklama bilgisi seçenekleri) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /debugtype
dev_langs:
- C++
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce4db4403f034a5795237393a8f1465fdf31982b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681087"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (Hata Ayıklama Bilgisi Seçenekleri)
/DEBUGTYPE seçeneği/Debug seçeneği tarafından oluşturulan hata ayıklama bilgileri türlerini belirtir.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## <a name="arguments"></a>Arguments  
 CV  
 Simgeler, satır numaraları ve diğer nesne derleme bilgileri PDB dosyası için hata ayıklama bilgileri yayılamıyor söyler. Varsayılan olarak, bu seçenek etkin olduğunda **/DEBUG** belirtilir ve **/DEBUGTYPE** belirtilmedi.  
  
 PDATA  
 .Pdata ve .xdata giriş PDB dosyası hata ayıklama akış bilgilerini eklemek için söyler. Varsayılan olarak, bu seçenek etkin olduğunda hem **/DEBUG** ve **Driver/Driver** seçenekler belirtilir. Varsa **/DEBUGTYPE:PDATA** belirtilen kendisi tarafından bağlayıcı otomatik olarak içerir PDB dosyasında hata ayıklama. Varsa **/DEBUGTYPE:PDATA, düzeltme** belirtildiğinde, bağlayıcı PDB dosyasında hata ayıklama içermez.  
  
 DÜZELTME  
 PDB dosyası hata ayıklama akış bilgilerini konum değiştirme tablosu girdileri eklemek için söyler. Varsayılan olarak, bu seçenek etkin olduğunda hem **/DEBUG** ve **/PROFILE** seçenekler belirtilir. Varsa **/DEBUGTYPE:FIXUP** veya **/DEBUGTYPE:FIXUP, PDATA** belirtildiğinde, bağlayıcı PDB dosyasında hata ayıklama içermez.  
  
 Bağımsız değişkenleri **/DEBUGTYPE** herhangi bir sırada virgül ile ayırarak birleştirilebilir. **/DEBUGTYPE** seçenek ve bağımsız değişkenlerinden büyük küçük harfe duyarlı değildir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım **/DEBUGTYPE** konum değiştirme tablosu veri veya .pdata ve .xdata başlık bilgilerini dahil edilmesi hata ayıklama akışında belirtmek için seçeneği. Bu, çekirdek modu kodu bozucu bir çekirdek hata ayıklayıcısı içinde görülebilir kullanıcı modu kodu hakkında bilgi dahil etmesini bağlayıcıya neden olur. Hata ayıklama simgeleri ne zaman kullanılabilir hale getirmek **düzeltme** olduğundan belirtilen dahil **CV** bağımsız değişken.  
  
 Uygulamalar için tipik olan kullanıcı modu kodunda hata ayıklamak için **/DEBUGTYPE** seçeneği gerekli olmayan. Varsayılan olarak, hata ayıklama belirten derleyici anahtarları çıktı ([/z7, / zi, /zı](../../build/reference/z7-zi-zi-debug-information-format.md)) tüm bilgileri Visual Studio hata ayıklayıcı gösterin. Kullanım **/DEBUGTYPE:PDATA** veya **/DEBUGTYPE:CV, PDATA, düzeltme** bir aygıt sürücüsü için bir yapılandırma uygulaması gibi kullanıcı modu hem de çekirdek modu bileşenlerini bir araya getiren kod hatalarını ayıklamak için. Çekirdek modu hata ayıklayıcıları hakkında daha fazla bilgi için bkz: [hata ayıklama araçları için Windows (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ DEBUG (hata ayıklama bilgileri üret)](../../build/reference/debug-generate-debug-info.md)   
 [/ DRIVER (Windows NT Çekirdek modu sürücüsü)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [/ PROFILE (performans araçları Profiler)](../../build/reference/profile-performance-tools-profiler.md)   
 [(WinDbg, KD, CDB, NTSD) Windows için hata ayıklama araçları](/windows-hardware/drivers/debugger/index)