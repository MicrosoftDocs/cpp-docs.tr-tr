---
title: "Derleme olaylarını belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
dev_langs: C++
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43f12e28487a4e162a88eaf0881ac9e50391e1f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="specifying-build-events"></a>Derleme Olayları Belirtme
Derleme olayları yapı başlamadan önce bağlantı işlemi, veya yapı tamamlandıktan sonra çalışan komutlar belirtmek için kullanabilirsiniz.  
  
 Yalnızca derleme derleme işlemindeki bu noktalarına başarıyla ulaşırsa derleme olaylarını yürütülür. Derlemede bir hata oluşursa, *oluşturma sonrası* olay gerçekleşmez; bağlama aşamasından önce hata oluşursa, *bağlama öncesi* veya *oluşturma sonrası* olay olur oluşur. Buna ek olarak, hiçbir dosya bağlanacak şekilde gerekiyorsa *bağlama öncesi* olay gerçekleşmez. *Bağlama öncesi* olay ayrıca bir bağlantı adımı içermez projelerinde kullanılabilir değil.  
  
 Hiçbir dosya oluşturulması gerekiyorsa, hiçbir derleme olaylarını ortaya çıkar.  
  
 Derleme olayları hakkında genel bilgi için bkz: [anlama özel derleme adımlarını ve derleme olaylarını](../ide/understanding-custom-build-steps-and-build-events.md).  
  
### <a name="to-specify-a-build-event"></a>Derleme olayının belirtmek için  
  
1.  İçinde **Çözüm Gezgini**, yapı olay belirtmek istediğiniz projeyi seçin.  
  
2.  Projenin açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
3.  İçinde **yapı olayları** klasörü, bir derleme olay özelliği sayfasını seçin.  
  
4.  Yapı olayla ilişkili özelliklerini belirtin:  
  
    -   İçinde **komut satırı**, komut isteminde belirtme gibi bir komutu belirtin. Geçerli bir komut veya toplu iş dosyasını belirtin ve gerekli giriş veya çıkış dosyaları. Belirtin **çağrısı** toplu tüm komutlar yürütülür güvence altına almak için bir toplu iş dosyası adından önce komutu.  
  
         Birden çok girdi ve çıktı dosyası sembolik olarak MSBuild makroları ile belirtilebilir. [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)]dosyalarının konumu ya da ayarlar, dosyaların adlarını belirtme [derleme komutları ve özellikler için ortak makrolar](../ide/common-macros-for-build-commands-and-properties.md).  
  
         Bir ortam değişkeni yerine her belirtirseniz, '%' karakteri MSBuild tarafından ayrılmış olduğundan  **%**  kaçış karakteri ile **% 25** onaltılık çıkış dizisi. Örneğin, **% WINDIR %** ile **25WINDIR % 25**. MSBuild değiştirir her **% 25** ile sıra  **%**  ortam değişkeni erişim izni vermeden önce karakter.  
  
    -   İçinde **açıklama**, bu olay için bir açıklama yazın. Açıklama için basılır **çıkış** bu olay oluştuğunda penceresi.  
  
    -   İçinde **gelen dışlanan yapı**, belirtin **Evet** çalıştırmak için olay istemiyorsanız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel derleme adımlarını ve derleme olaylarını anlama](../ide/understanding-custom-build-steps-and-build-events.md)   
 [Derleme komutları ve özellikler için ortak makroları](../ide/common-macros-for-build-commands-and-properties.md)   
 [Derleme özelleştirmeleri sorunlarını giderme](../ide/troubleshooting-build-customizations.md)