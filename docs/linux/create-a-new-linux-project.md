---
title: Visual Studio'da yeni bir C++ Linux projesi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 07/20/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: f64f8eaf09e92df3dd776180db5904af039d6ad7
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207976"
---
# <a name="create-a-new-linux-project"></a>Yeni Linux projesi oluşturma
Linux için Visual Studio'da C++ kodlama, Visual Studio projesi ya da bir CMake projesini oluşturma seçeneğiniz vardır. Bu konuda, Visual Studio projesi oluşturma işlemini açıklar. CMake projeleri hakkında daha fazla bilgi için bkz: [Linux CMake projesi yapılandırma ](cmake-linux-project.md).

Visual Studio'da yeni Linux projesi oluşturmak için aşağıdakileri yapın:

1. Seçin **Dosya > Yeni proje** Visual Studio'da ya da tuşuna **Ctrl + Shift + N**.
1. Seçin **Visual C++ > Çoklu Platform > Linux** düğümünü ve ardından oluşturmak istediğiniz proje türü adı/konum girin ve Tamam'a tıklayın.

   ![Yeni Linux projesi](media/newproject.png)

   | Proje türü | Açıklama
   | ------------ | ---
   | **Yanıp sönme (Raspberry)**           | Raspberry Pi'yi cihaz için bir yanıp sönme yazılan örnek kod ile hedeflenen proje
   | **Konsol uygulaması (Linux)** | Proje metin konsola çıktı olarak yazılan örnek kod ile herhangi bir Linux bilgisayar için hedeflenmiş
   | **Boş proje (Linux)**       | Örnek kod olmadan yazılan herhangi bir Linux bilgisayar için hedeflenen bir proje
   | **Derleme görevleri dosyası projesi (Linux)**    | Derleme sistemi, standart bir derleme görevleri dosyası kullanılarak oluşturulan Linux bilgisayar için hedeflenen bir proje

