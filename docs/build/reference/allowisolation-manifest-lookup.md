---
title: -ALLOWISOLATION (bildirim arama) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0e063aa51e136dfcc7a4445948e8a68d7a99bca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Bildirim Arama)
Bildirim arama davranışını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ALLOWISOLATION:No** DLL'leri hiçbir bildirim boşmuş gibi yüklenir gösterir ve ayarlamak bağlayıcı neden `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` isteğe bağlı başlığının içinde bit `DllCharacteristics` alan.  
  
 **/ ALLOWISOLATION** işletim sisteminin aramaları ve yükleri bildirim neden olur.  
  
 **/ ALLOWISOLATION** varsayılandır.  
  
 Yalıtım için yürütülebilir bir dosya devre dışı bırakıldığında, yeni oluşturulan işlemi için bir uygulama bildirimi bulmak Windows Yükleyici çalışmaz. Yeni işlem olsa bile bir bildirim çalıştırılabilir veya yürütülebilir dosya adı ile aynı dizinde yerleştirilen içinde varsayılan etkinleştirme bağlamı olmaz * yürütülebilir-name ***. exe.manifest**.  
  
 Daha fazla bilgi için bkz: [bildirim dosyaları başvuru](http://msdn.microsoft.com/library/aa375632).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **bildirim dosyası** özellik sayfası.  
  
5.  Değiştirme **izin yalıtım** özelliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)