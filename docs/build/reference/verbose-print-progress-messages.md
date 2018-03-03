---
title: "-VERBOSE (ilerleme iletilerini Yazdır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
dev_langs:
- C++
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76ead441a8dc7ec65a6966371b83d42c47c897c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (İlerleme İletilerini Yazdır)
```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı bağlama oturumuna ilerleme durumu hakkında bilgi gönderir **çıkış** penceresi. Komut satırında bilgileri standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|/ VERBOSE|Bağlama işleminin ayrıntılarını görüntüler.|  
|/ VERBOSE: ICF|Kullanımından sonuçları bağlayıcı etkinliği hakkında bilgi görüntüler [/OPT:ICF](../../build/reference/opt-optimizations.md).|  
|/ VERBOSE: INCR|Artımlı bağlantı işlemi hakkında bilgileri görüntüler.|  
|/ VERBOSE: LIB|Yalnızca kitaplıkları belirtmek ilerleme durumu iletileri görüntüler aranır.<br /><br /> Görüntülenen bilgileri Kitaplığı arama işlemi içerir ve her kitaplığı ve nesne adını (tam yolu) listeler, simgenin kitaplık ve simgenin başvuru nesnelerin bir listesini çözümleniyor.|  
|/ VERBOSE: BAŞVURU|Kullanımından sonuçları bağlayıcı etkinliği hakkında daha fazla bilgi görüntüler [/OPT:REF](../../build/reference/opt-optimizations.md).|  
|/ VERBOSE: SAFESEH|Ne zaman güvenli özel durum işleme ile uyumlu olmayan modüller hakkında daha fazla bilgi görüntüler [SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) belirtilmedi.|  
|/ VERBOSE: UNUSEDLIBS|Görüntü oluşturulduğunda kullanılmayan tüm kitaplık dosyalar hakkındaki bilgileri görüntüler.|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **bağlayıcı** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Seçeneğini eklemek **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)