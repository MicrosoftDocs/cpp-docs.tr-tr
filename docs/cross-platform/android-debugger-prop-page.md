---
title: Android hata ayıklayıcı özellikleriC++()
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 8ff6e539828d697e103c820d05565969f6afb910
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78177530"
---
# <a name="android-debugger-properties"></a>Android hata ayıklayıcı özellikleri

Özellik | Açıklama | Yapabileceği
--- | ---| ---
Hata ayıklayıcı türü | Hata ayıklamanın hangi kod türünde olduğunu belirtir. | **Yalnızca yerel**<br>**Yalnızca Java**<br>
Hata ayıklama hedefi | Hata ayıklama için kullanılacak öykünücüyü veya cihazı belirtir. Hiçbir öykünücü çalışmıyorsa, bir cihazı başlatmak için ' Android sanal cihazı (AVD) Yöneticisi ' ni kullanın.
Başlatılacak paket | Hata ayıklaması yapılacak *. apk* konumunu belirtir. Bu seçenek, uygulamanın hatası ayıklandığında paketi (APK) başlatır.
Başlatma etkinliği | Uygulamayı başlatmak için kullanılacak Android etkinliği, bildirimde kullanılan bir ile eşleşmelidir. *AndroidManifest. xml* dosyasından listeyi almak ve dinamik olarak doldurmak için Uygula ' ya basın.
Ek sembol arama yolları | Hata ayıklama sembolleri için ek arama yolu.
Ek Java kaynağı arama yolları | Java kaynak dosyaları için ek arama yolları. (Yalnızca hata ayıklayıcı türü yalnızca Java olduğunda geçerlidir.)
