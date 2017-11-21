---
title: "-DEBUGTYPE (hata ayıklama bilgisi seçenekleri) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /debugtype
dev_langs: C++
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7532f0ceb39db4ff2ff44a6cca9076034ece3114
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (Hata Ayıklama Bilgisi Seçenekleri)
/DEBUGTYPE seçeneği/Debug seçeneğini tarafından oluşturulan hata ayıklama bilgisi türlerini belirtir.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## <a name="arguments"></a>Arguments  
 MS  
 Simgeler, satır numaralarını ve diğer nesne derleme bilgileri PDB dosyasında hata ayıklama bilgisi yayması için bağlayıcı söyler. Varsayılan olarak, bu seçenek etkin olduğunda **/DEBUG** belirtilir ve **/DEBUGTYPE** belirtilmedi.  
  
 PDATA  
 PDB dosyasında hata ayıklama akışı bilgilerini ve.xdata'yı ve sanal işlem bulunur girişleri eklemek için bağlayıcı söyler. Varsayılan olarak, bu seçenek etkinleştirildiğinde, hem **/DEBUG** ve **/sürücü** seçenekleri belirtilir. Varsa **/DEBUGTYPE:PDATA** belirtilen kendisi tarafından bağlayıcı otomatik olarak içeren hata ayıklama simgeleri PDB dosyasında. Varsa **/DEBUGTYPE:PDATA, düzeltmesi** belirtilirse, bağlayıcı hata ayıklama simgeleri PDB dosyasındaki içermez.  
  
 DÜZELTMESİ  
 PDB dosyasında hata ayıklama akışı bilgilerini yeniden konumlandırma tablosu girdileri eklemek için bağlayıcı söyler. Varsayılan olarak, bu seçenek etkinleştirildiğinde, hem **/DEBUG** ve **/PROFİL** seçenekleri belirtilir. Varsa **/DEBUGTYPE:FIXUP** veya **/DEBUGTYPE:FIXUP, PDATA** belirtilirse, bağlayıcı hata ayıklama simgeleri PDB dosyasındaki içermez.  
  
 Bağımsız değişkenleri **/DEBUGTYPE** herhangi bir sırada virgül ile ayırarak birleştirilebilir. **/DEBUGTYPE** seçeneği ve bağımsız değişkenlerini büyük küçük harfe duyarlı değildir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım **/DEBUGTYPE** eklenmesi yeniden konumlandırma tablo verileri veya ve.xdata'yı ve sanal işlem bulunur üst bilgileri, hata ayıklama akışta belirtmek için seçeneği. Bu, çekirdek modu kodunda kesme çekirdek hata ayıklayıcısı'ndaki görülebilir kullanıcı modu kodu hakkında bilgi dahil etmek bağlayıcı neden olur. Hata ayıklama simgeleri ne zaman kullanılabilir hale getirmek **düzeltmesi** olduğu belirtilen dahil **MS** bağımsız değişkeni.  
  
 Uygulamalar için genel bir durumdur, kullanıcı modunda kod hatalarını ayıklamak için **/DEBUGTYPE** seçenek gerekli değildir. Varsayılan olarak, hata ayıklama belirtin derleyici anahtarları çıktı ([/Z7, / zi, /zı](../../build/reference/z7-zi-zi-debug-information-format.md)) tüm bilgileri tarafından Visual Studio hata ayıklayıcısı yayma. Kullanım **/DEBUGTYPE:PDATA** veya **/DEBUGTYPE:CV, PDATA, düzeltmesi** bir aygıt sürücüsü için bir yapılandırma uygulama gibi kullanıcı modu ile çekirdek modu bileşenleri birleştirir kodun hatalarını ayıklamak için. Çekirdek modu hata ayıklayıcıları hakkında daha fazla bilgi için bkz: [Windows hata ayıklama araçları için (WinDbg, KD, CDB, NTSD)](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ DEBUG (hata ayıklama bilgileri üret)](../../build/reference/debug-generate-debug-info.md)   
 [/ DRIVER (Windows NT Çekirdek modu sürücüsü)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [/ PROFILE (performans araçları Profil Oluşturucusu)](../../build/reference/profile-performance-tools-profiler.md)   
 [Windows (WinDbg, KD, CDB, NTSD) için hata ayıklama araçları](http://go.microsoft.com/fwlink/p?LinkID=285651)