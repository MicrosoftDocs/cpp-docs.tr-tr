---
title: Mevcut koddan yeni proje yapılandırmasını Release | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.releasesettings
dev_langs:
- C++
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4e7d5fb707c455aa7b7fb9f0e14dff95ee5633f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703371"
---
# <a name="specify-release-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Yayın Yapılandırma Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı
Oluşturma yeni proje varolan kod dosyalarından sihirbazın bu sayfası, proje ayarları belirtmek için kullanın.  
  
## <a name="task-list"></a>Görev Listesi  
 [Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement Listesi  
- **Hata ayıklama yapılandırması ile aynı**

   Sihirbazı için hata ayıklama yapılandırması proje ayarları sürüm yapılandırması proje ayarları aynı oluşturacağını belirtir. Bu seçenek varsayılan olarak denetlenir. Bu kutunun işaretini kaldırın sürece bu sayfadaki diğer tüm seçenekler devre dışıdır.  
  
- **Komut satırı derleme**

   Yeni projeyi derler komut satırını belirtir. Derleyici yanı sıra anahtarları veya yeni projeyi oluşturmak için kullanmak istediğiniz bağımsız değişken adını girin. Bu seçenek etkin olduğunda **kullanım dış derleme sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfası.  
  
- **Yeniden derle komut satırı**

   Yeni proje oluşturur. komut satırı belirtir. Bu seçenek etkin olduğunda **kullanım dış derleme sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfası.  
  
- **Temizle komut satırı**

   Yeni proje için yapı araçları tarafından oluşturulan destek dosyalarını silmek için komut satırını belirtir. Bu seçenek etkin olduğunda **kullanım dış derleme sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfası.  
  
- **Çıkış (hata ayıklama için)**

   Yeni projenin hata ayıklama yapılandırması için çıkış dosyalarının dizin yolunu belirtir. Bu seçenek etkin olduğunda **kullanım dış derleme sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfası.  
  
- **Önişlemci tanımları (/ D)**

   Yeni proje için önişlemci sembolleri tanımlar. Daha fazla bilgi için [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md).  
  
- **Arama Yolu Ekle (/ ı)**

   Ön İşlemci yönergelerinde yeni proje için geçirilen dosya başvurularını çözümlemek için derleyicinin arama yapacağı dizinleri listesine eklemek için dizin yolu belirtir. Daha fazla bilgi için [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md).  
  
- **Zorunlu eklenen dosyalar (/FI)**

   Yeni proje oluştururken işlenecek üst bilgi dosyaları belirtir. Daha fazla bilgi için [/FI (zorla dahil dosyasını Adlandır)](../build/reference/fi-name-forced-include-file.md).  
  
- **.NET bütünleştirilmiş kod arama yolu (/ AI)**

   Ön İşlemci yönergelerinde yeni proje için .NET derleme başvurularını çözümlemek için derleyicinin arama yapacağı dizin yolları geçirildi belirler. Daha fazla bilgi için [/AI (meta veri dizinlerini belirtin)](../build/reference/ai-specify-metadata-directories.md).  
  
- **Zorunlu .NET derlemeleri (/ FU)**

   Yeni proje oluştururken işlenecek .NET bütünleştirilmiş kodları belirtir. Daha fazla bilgi için [/FU (zorlanan adı #using)](../build/reference/fu-name-forced-hash-using-file.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)