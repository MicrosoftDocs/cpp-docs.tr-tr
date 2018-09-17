---
title: Mevcut koddan yeni proje ayarı (Visual C++) hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.debugsettings
dev_langs:
- C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4139b5bf994a2034ad243fb3351c44847f3a85bf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709650"
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Yapılandırma Ayarlarında Hata Ayıklamayı Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı
Oluşturma yeni proje varolan kod dosyalarından sihirbazın bu sayfası, hata ayıklama yapılandırması proje ayarları belirtmek için kullanın.  
  
## <a name="task-list"></a>Görev Listesi  
[Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement Listesi  
- **Komut satırı derleme**

   Yeni projeyi derler komut satırını belirtir. Örneğin, derleyici (artı herhangi anahtarlar ve bağımsız değişkenler) adını girin veya yeni projeyi oluşturmak için kullanmak istediğiniz derleme betikleri. Bu seçenek etkin olduğunda **kullanım dış yapı sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfasında; Aksi takdirde kullanılamıyor.  
  
- **Yeniden derle komut satırı**

   Yeni proje oluşturur. komut satırı belirtir. Bu seçenek etkin olduğunda **kullanım dış yapı sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfasında; Aksi takdirde kullanılamıyor.  
  
- **Temizle komut satırı**

   Yeni proje için yapı araçları tarafından oluşturulan destek dosyalarını silmek için komut satırını belirtir. Bu seçenek etkin olduğunda **kullanım dış yapı sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfasında; Aksi takdirde kullanılamıyor.  
  
- **Çıkış (hata ayıklama için)**

   Yeni projenin hata ayıklama yapılandırması için çıkış dosyalarının dizin yolunu belirtir. Bu seçenek etkin olduğunda **kullanım dış yapı sistemi** seçeneği seçildiğinde, **proje ayarlarını belirtme** sayfasında; Aksi takdirde kullanılamıyor.  
  
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
