---
title: 'Nasıl yapılır: Varolan koddan C++ projesi oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09b190dbc2670ab94f7952adc188dd43d91fb520
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397292"
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma

Visual Studio'da, varolan kod dosyalarınızı bir Visual C++ projesine kullanarak bağlantı noktası **oluşturma yeni proje varolan kod dosyalarından** Sihirbazı. Bu sihirbaz, Visual Studio'nun eski Express sürümlerinde kullanılamaz. Bu sihirbaz, yeni çözüm ve kaynak dosyalarını yönetme ve yapılandırma oluşturmak için MSBuild sistemi kullanan proje oluşturur.

Varolan kod dosyalarınızı bir Visual C++ projesine taşımak, tüm IDE içine yerleşik yerel MSBuild proje yönetimi özelliklerini kullanmanıza olanak sağlar. Nmake derleme görevleri dosyalarını, CMake veya alternatifleri gibi var olan, derleme sisteminizi kullanmayı tercih ederseniz, bunun yerine klasörü Aç seçeneği kullanabilirsiniz. Daha fazla bilgi için [Klasör Aç Visual C++ projelerinde](../ide/non-msbuild-projects.md). İki seçenek de gibi IDE özelliklerini kullanmanıza izin [IntelliSense](/visualstudio/ide/using-intellisense) ve [proje özellikleri](../ide/working-with-project-properties.md).

### <a name="to-create-a-c-project-from-existing-code"></a>Varolan koddan bir C++ projesi oluşturmak için

1. Üzerinde **dosya** menüsünde **yeni**ve ardından **varolan koddan proje**.

1. ' Nın ilk sayfasında **varolan kod dosyalarından yeni proje oluştur** seçin **Visual C++** içinde **ne tür bir proje oluşturmak istersiniz** listesi. Seçin **sonraki** devam etmek için.

1. Proje konumunuz ve kaynak dosyalarını dizinini belirtin. Bu sayfa hakkında daha fazla bilgi için bkz: [proje konumu belirtin ve kaynak dosyaları oluşturma yeni proje varolan kod dosyaları sihirbazın](../ide/specify-project-location-and-source-files.md). Seçin **sonraki** devam etmek için.

1. Kullanmak için proje ayarlarını belirtin. Bu sayfa hakkında daha fazla bilgi için bkz: [proje ayarlarını belirtme, oluşturma yeni proje varolan kod dosyaları sihirbazın](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md). Seçin **sonraki** devam etmek için.

1. Hata ayıklama yapılandırma ayarlarını belirtin. Bu sayfa hakkında daha fazla bilgi için bkz: [hata ayıklama yapılandırma ayarlarını belirtin, oluşturma yeni proje varolan kod dosyaları sihirbazın](../ide/specify-debug-configuration-settings.md). Seçin **sonraki** devam etmek için.

1. Sürüm yapılandırma ayarlarını belirtin. Bu sayfa hakkında daha fazla bilgi için bkz: [sürüm yapılandırma ayarlarını belirt, oluşturma yeni proje varolan kod dosyaları sihirbazın](../ide/specify-release-configuration.md). Seçin **son** yeni projeyi oluşturmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[Proje Konumunu ve Kaynak Dosyaları Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-project-location-and-source-files.md)<br>
[Proje Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)<br>
[Yapılandırma Ayarlarında Hata Ayıklamayı Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-debug-configuration-settings.md)<br>
[Yayın Yapılandırma Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-release-configuration.md)