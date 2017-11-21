---
title: "Var olan koddan yeni proje ayarı (Visual C++) hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.debugsettings
dev_langs: C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1781d5c5bba0d818111673594a5526354a490bd7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Yapılandırma Ayarlarında Hata Ayıklamayı Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı
Hata ayıklama yapılandırması proje ayarları belirtmek için bu sayfayı oluşturmak yeni proje varolan kod dosyaları Sihirbazı kullanın.  
  
## <a name="task-list"></a>Görev Listesi  
 [Nasıl yapılır: Varolan koddan C++ projesi oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Komut satırı derleme**  
 Yeni Proje derlemeler komut satırını belirtir. Örneğin, derleyici (artı tüm anahtarları ve bağımsız değişkenler) adını girin veya yapı yeni proje oluşturmak için kullanmak istediğiniz komut dosyası. Bu seçenek etkinleştirildiğinde zaman **kullanım Dış Sistem yapı** seçeneği seçildiğinde, **proje ayarlarını belirt** sayfasında; Aksi takdirde kullanılamıyor.  
  
 **Komut satırı yeniden oluşturma**  
 Yeni proje oluşturur komut satırını belirtir. Bu seçenek etkinleştirildiğinde zaman **kullanım Dış Sistem yapı** seçeneği seçildiğinde, **proje ayarlarını belirt** sayfasında; Aksi takdirde kullanılamıyor.  
  
 **Temiz komut satırı**  
 Yeni proje için derleme araçları tarafından oluşturulan destek dosyaları silmek için komut satırını belirtir. Bu seçenek etkinleştirildiğinde zaman **kullanım Dış Sistem yapı** seçeneği seçildiğinde, **proje ayarlarını belirt** sayfasında; Aksi takdirde kullanılamıyor.  
  
 **Çıktı (için hata ayıklama)**  
 Yeni Proje hata ayıklama yapılandırması için çıkış dosyalarının dizin yolunu belirtir. Bu seçenek etkinleştirildiğinde zaman **kullanım Dış Sistem yapı** seçeneği seçildiğinde, **proje ayarlarını belirt** sayfasında; Aksi takdirde kullanılamıyor.  
  
 **Önişlemci tanımları (/ D)**  
 Yeni proje için önişlemci simgelerini tanımlar. Daha fazla bilgi için bkz: [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md).  
  
 **Arama Yolu Ekle (/ t)**  
 Önişlemci yönergeleri yeni proje dosyası başvuruları çözümlemek için geçirilen derleyici arama dizinleri listesine eklemek için dizin yolu belirtir. Daha fazla bilgi için bkz: [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md).  
  
 **Zorlanmış eklenen dosyalar (/FI)**  
 Yeni proje oluşturulurken işlemek için üstbilgi dosyaları belirtir. Daha fazla bilgi için bkz: [/FI (zorla dahil dosyasını Adlandır)](../build/reference/fi-name-forced-include-file.md).  
  
 **.NET derleme arama yolu (/ AI)**  
 Önişlemci yönergeleri yeni projede derleyici .NET derleme başvuruları çözümlemek için arayacağı dizin yolları geçirilecek belirtir. Daha fazla bilgi için bkz: [/AI (meta veri dizinlerini belirtin)](../build/reference/ai-specify-metadata-directories.md).  
  
 **.NET derlemelerini kullanarak zorla (/ FU)**  
 Yeni proje oluşturulurken işlemek için .NET derlemelerini belirtir. Daha fazla bilgi için bkz: [/FU (zorlanan adı #using)](../build/reference/fu-name-forced-hash-using-file.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ayarlarını belirtme, varolan kod dosyaları Sihirbazı'ndan yeni proje oluşturma](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)
