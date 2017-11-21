---
title: -ALLOWISOLATION (bildirim arama) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs: C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c8d6163c6377a6d8c92875b3bb5ba76b07a94d38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 Yalıtım için yürütülebilir bir dosya devre dışı bırakıldığında, yeni oluşturulan işlemi için bir uygulama bildirimi bulmak Windows Yükleyici çalışmaz. Yeni işlem olsa bile bir bildirim çalıştırılabilir veya yürütülebilir dosya adı ile aynı dizinde yerleştirilen içinde varsayılan etkinleştirme bağlamı olmaz *yürütülebilir dosya adı***. exe.manifest**.  
  
 Daha fazla bilgi için bkz: [bildirim dosyaları başvuru](http://msdn.microsoft.com/library/aa375632).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **bildirim dosyası** özellik sayfası.  
  
5.  Değiştirme **izin yalıtım** özelliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)