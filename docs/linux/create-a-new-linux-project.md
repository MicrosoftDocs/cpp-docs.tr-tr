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
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 8b9eda4c238ae1a3ea3e59d0e5c39ee6b59cff02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

