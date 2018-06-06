---
title: Derleme olaylarını belirtme | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5940f0d6efaec402a4a85ed659f42d7eab1bf91d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33334970"
---
# <a name="specifying-build-events"></a>Derleme olayları belirtme

Derleme olayları yapı başlamadan önce bağlantı işlemi, veya yapı tamamlandıktan sonra çalışan komutlar belirtmek için kullanabilirsiniz.

Yalnızca derleme derleme işlemindeki bu noktalarına başarıyla ulaşırsa derleme olaylarını yürütülür. Derlemede bir hata oluşursa, *oluşturma sonrası* olay oluşmaz; bağlama aşamasından önce hata oluşursa, *bağlama öncesi* veya *oluşturma sonrası* olayı oluşur. Buna ek olarak, hiçbir dosya bağlanacak şekilde gerekiyorsa *bağlama öncesi* olay oluşmaz. *Bağlama öncesi* olay ayrıca bir bağlantı adımı içermez projelerinde kullanılabilir değil.

Hiçbir dosya oluşturulması gerekiyorsa, hiçbir derleme olayları oluşur.

Derleme olayları hakkında genel bilgi için bkz: [anlama özel derleme adımlarını ve derleme olaylarını](../ide/understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-build-event"></a>Derleme olayının belirtmek için

1. İçinde **Çözüm Gezgini**, yapı olay belirtmek istediğiniz projeyi seçin.

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).

1. İçinde **yapı olayları** klasörü, bir derleme olay özelliği sayfasını seçin.

1. Yapı olayla ilişkili özelliklerini belirtin:

   - İçinde **komut satırı**, komut isteminde belirtme gibi bir komutu belirtin. Geçerli bir komut veya toplu iş dosyasını belirtin ve gerekli giriş veya çıkış dosyaları. Belirtin **çağrısı** toplu tüm komutlar yürütülür güvence altına almak için bir toplu iş dosyası adından önce komutu.

      Birden çok girdi ve çıktı dosyası sembolik olarak MSBuild makroları ile belirtilebilir. Dosyalarının konumu veya dosya kümelerini adlarını belirtme hakkında daha fazla bilgi için bkz: [derleme komutları ve özellikler için ortak makrolar](../ide/common-macros-for-build-commands-and-properties.md).

      Bir ortam değişkeni yerine her belirtirseniz, '%' karakteri MSBuild tarafından ayrılmış olduğundan **%** kaçış karakteri ile **% 25** onaltılık çıkış dizisi. Örneğin, **% WINDIR %** ile **25WINDIR % 25**. MSBuild değiştirir her **% 25** ile sıra **%** ortam değişkeni erişim izni vermeden önce karakter.

   - İçinde **açıklama**, bu olay için bir açıklama yazın. Açıklama yazdırıldığında **çıkış** bu olay oluştuğunda penceresi.

   - İçinde **gelen dışlanan yapı**, belirtin **Evet** çalıştırmak için olay istemiyorsanız.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../ide/understanding-custom-build-steps-and-build-events.md)  
[Genel Derleme Komutları ve Özellikler Makroları](../ide/common-macros-for-build-commands-and-properties.md)  
[Derleme Özelleştirmeleri Sorunlarını Giderme](../ide/troubleshooting-build-customizations.md)  
