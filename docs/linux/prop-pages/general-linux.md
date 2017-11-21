---
title: "Genel Özellikler (Linux C++ projesi) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.UseOfSTL
ms.openlocfilehash: 4de08a00ddedf1eec97d1872646a986e09c22547
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="general-properties-linux-c"></a>Genel Özellikler (Linux C++)

Özellik | Açıklama | Seçenekler
--- | ---| ---
Çıktı dizini | Çıktı dosyası dizini için göreli bir yol belirtir; ortam değişkenleri içerebilir.
Ara dizini | Ara dosyası dizine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Hedef Adı | Bu proje oluşturacak olan bir dosya adını belirtir.
Hedef uzantısı | Bu proje oluşturacak olan bir dosya uzantısı belirtir. (Örnek: bir)
Temiz üzerinde silme uzantıları | Joker karakter belirtimi üzerinde temiz silmek veya yeniden ara dizinde hangi dosyalarını noktalı virgülle ayrılmış.
Günlük dosyası oluşturma | Günlük ne zaman oluşturulacağını etkin yazmak için yapılandırma günlük dosyasını belirtir.
Platform araç takımı | Geçerli yapılandırma oluşturmak için kullanılan araç takımı belirtir; Aksi halde kümesi, varsayılan araç takımı kullanılır.
Uzak yapı makinesi | Hedef makine ya da uzak yapı için kullanmak üzere cihaz dağıtmak ve hata ayıklama.
Uzak derleme kök dizini | Uzak makinenin veya cihazın bir dizin yolunu belirtir.
Uzak derleme proje dizini | Uzak makinede veya aygıt proje için bir dizin yolunu belirtir.
Yapılandırma türü | Bu yapılandırma oluşturur çıktı türünü belirtir. | **Dinamik kitaplığı (.so)** -dinamik kitaplığı (.so)<br>**Statik kitaplık (bir)** -statik kitaplık (bir)<br>**Uygulama (.out)** -uygulama (.out)<br>**Derleme görevleri dosyası** -derleme görevleri dosyası<br>
STL kullanımı | Bu yapılandırma için kullanmak üzere hangi C++ Standart Kitaplığı belirtir. | **Paylaşılan GNU standart C++ Kitaplığı**<br>**Statik GNU standart C++ Kitaplığı (-statik)**<br>
