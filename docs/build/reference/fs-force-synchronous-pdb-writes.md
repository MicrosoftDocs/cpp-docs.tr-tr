---
title: -FS (zaman uyumlu PDB yazmalarını zorla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FS
dev_langs:
- C++
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8565022a77742a1a8c7ed1f243a192d94c8627fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374797"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (Zaman Uyumlu PDB Yazmalarını Zorla)
Zorlar program veritabanı (PDB) dosyasına yazar — tarafından oluşturulan [/zı](../../build/reference/z7-zi-zi-debug-information-format.md) veya [/zı](../../build/reference/z7-zi-zi-debug-information-format.md)— MSPDBSRV serileştirilmesi için. EXE.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/FS  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, zaman **/zı** veya **/zı** belirtilirse, derleyicinin türü bilgilerini ve simgesel hata ayıklama bilgilerini yazmak için PDB dosyalarını kilitler. Bu, derleyicinin türlerinin sayısı büyük olduğunda türü bilgileri oluşturmak için gereken süreyi önemli ölçüde azaltabilir. Başka bir işlem PDB dosya geçici olarak kilitler — Örneğin, bir virüsten koruma programı — derleyici tarafından yazma başarısız olabilir ve önemli bir hata oluşabilir. Cl.exe birden çok kopyasının aynı PDB dosyası eriştiğinizde Bu sorun ayrıca oluşabilir — Örneğin, çözümünüzü bağımsız varsa aynı projeleri ara dizinleri veya çıkış dizinleri ve paralel derlemeleri etkinleştirilir. **/FS** derleyici seçeneği derleyici PDB dosyası kilitlemelerini engeller ve MSPDBSRV gitmek için yazma zorlar. EXE erişim serileştirir. Bu derlemeleri önemli ölçüde uzun hale getirebilir ve cl.exe birden çok örneği aynı anda PDB dosyası eriştiğinizde oluşabilecek tüm hatalar engellemez. Böylece bağımsız projeleri Ara ayırmak yazma ve çıktı konumlarını ya da sizin olun projelerden biri diğerine bağımlı serileştirilmiş zorla proje derlemeleri çözümünüzü değiştirmenizi öneririz.  
  
 [/MP](../../build/reference/mp-build-with-multiple-processes.md) seçeneği belirlendiğinde **/FS** varsayılan olarak.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** eklenecek özellik `/FS` ve ardından **Tamam**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)