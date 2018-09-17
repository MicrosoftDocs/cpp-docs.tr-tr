---
title: Yeni Proje varolan kod - kaynak dosyaları (Visual C++) oluştur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.location
dev_langs:
- C++
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3647ad3211043a5356649cb5f350ec07009f2279
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707843"
---
# <a name="specify-project-location-and-source-files-create-new-project-from-existing-code-files-wizard"></a>Proje Konumunu ve Kaynak Dosyaları Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı
Oluşturma yeni proje varolan kod dosyalarından sihirbazın bu sayfası belirtmek için kullanın:  
  
-   Yeni Proje dizin yolu  
  
-   Mevcut kaynak dosyalarının aranacağı dizinler  
  
-   Sihirbaz yeni projeye alacak dosya türü  
  
## <a name="task-list"></a>Görev Listesi  
[Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement Listesi  
- **Proje dosya konumu**

   Yeni Proje dizini yolunu belirtir. Sihirbaz tüm dosyaları (ve alt dizinleri) yeni projenin nerede havale bu konumdur.  
  
- **Göz atma**

   Görüntüler **proje dosya konumu** iletişim kutusunda, yeni proje içeren dizini belirtin yardımcı olur. Bu denetim istenen klasörüne gitmenizi sağlar.  
  
- **Proje adı**

   Yeni proje adını belirtir. Bu ada sahip dosya uzantılarını .vcxproj gibi proje dosyaları, benimseyeceği. Varolan kod dosyaları, kendi özgün adı tutar.  
  
- **Dosyalar projeye bu klasörlerden ekleyin.**

   Bu onay kutusu işaretlendiğinde, varolan kod dosyaları (Bu, liste kutusunda Bu denetimin altında belirtilir), özgün dizin kopyalamak için Sihirbazı yeni projeye ayarlar.  
  
- **Alt klasörleri ekle**

   Dizinin tüm alt dizinlerden kod dosyaları kopyalamak için listelenen belirtir **klasör** yeni projeye sütun.  
  
- **Klasör**

   Varolan kod dosyaları yeni projeye kopyalayın içeren dizinin yolunu gösterir. Bu sütun, sihirbaz varolan kod dosyaları için arama yapacağı dizinleri listeler.  
  
- **Add**

   Görüntüler **ekleme dosyaları projeye bu klasörden** iletişim kutusunda, sihirbaz varolan kod dosyaları için arama yapacağı belirtin dizinleri yardımcı olur.  
  
- **Kaldır**

   Bu denetim listesi kutusu solundaki seçili dizin yolu siler.  
  
- **Projeye eklemek için dosya türleri**

   Sihirbazın belirli dosya uzantılarını temel alan yeni proje ekler dosya türlerini belirtir. Dosya uzantıları, yıldız işareti joker karakteriyle öncesinde ve noktalı virgülle ayrılmış dosya uzantıları listesinde.  
  
- **Çözüm Gezgini içindeki tüm dosyaları göster**

   Tüm dosyalar, Çözüm Gezgini penceresinde görünür ve görüntülenen yeni projeyi belirtir. Bu seçenek varsayılan olarak etkindir.