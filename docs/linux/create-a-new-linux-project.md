---
title: "Visual Studio'da yeni bir C++ Linux projesi oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31309f961b392cb7548c3114e1af8604ac872cf3
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="create-a-new-linux-project"></a>Yeni Linux projesi oluşturma
Linux için kodlama yaparken, Visual Studio projesi veya CMake projesi oluşturma seçeneğiniz vardır. Bu konuda bir Visual Studio projesi oluşturmayı açıklar. CMake projeler hakkında daha fazla bilgi için bkz: [bir Linux CMake proje yapılandırma ](cmake-linux-project.md).

Visual Studio'da yeni bir Linux projesi oluşturmak için aşağıdakileri yapın:

1. Seçin **Dosya > Yeni proje** Visual Studio ya da tuşuna **Ctrl + Shift + N**.
1. Seçin **Visual C++ > Çapraz Platform > Linux** düğümünü ve ardından oluşturmak için istediğiniz proje türü bir ad/konum girin ve Tamam'ı tıklatın.

   ![Yeni Linux projesi](media/newproject.png)

   | Proje türü | Açıklama
   | ------------ | ---
   | **Blink (Raspberry)**           | Örnek kod bir LED blink yazılan ile Raspberry Pi'yi aygıt için hedeflenen proje
   | **Konsol uygulaması (Linux)** | Proje metin konsola çıkarmak için yazılmış örnek kod ile herhangi bir Linux bilgisayar için hedeflenmiş
   | **Boş proje (Linux)**       | Yazılan hiçbir örnek kod olan herhangi bir Linux bilgisayar için hedeflenen proje
   | **Derleme görevleri dosyası projesi (Linux)**    | Standart bir derleme görevleri dosyası derleme sistemiyle yerleşik Linux bilgisayar için hedeflenen proje

