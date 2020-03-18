---
title: Android hata ayıklayıcı özellikleriC++()
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 3ac896b384181e4e2b436368f39a343d35fe321a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446889"
---
# <a name="android-debugger-properties"></a>Android hata ayıklayıcı özellikleri

| Özellik | Açıklama | Yapabileceği |
|--|--|--|
| Hata ayıklayıcı türü | Hata ayıklamanın hangi kod türünde olduğunu belirtir. | **Yalnızca yerel**<br /><br />**Yalnızca Java** |
| Hata ayıklama hedefi | Hata ayıklama için kullanılacak öykünücüyü veya cihazı belirtir. Hiçbir öykünücü çalışmıyorsa, bir cihazı başlatmak için ' Android sanal cihazı (AVD) Yöneticisi ' ni kullanın. |
| Başlatılacak paket | Hata ayıklaması yapılacak *. apk* konumunu belirtir. Bu seçenek, uygulamanın hatası ayıklandığında paketi (APK) başlatır. |
| Başlatma etkinliği | Uygulamayı başlatmak için kullanılacak Android etkinliği, bildirimde kullanılan bir ile eşleşmelidir. *AndroidManifest. xml* dosyasından listeyi almak ve dinamik olarak doldurmak için Uygula ' ya basın. |
| Ek sembol arama yolları | Hata ayıklama sembolleri için ek arama yolu. |
| Ek Java kaynağı arama yolları | Java kaynak dosyaları için ek arama yolları. (Yalnızca hata ayıklayıcı türü yalnızca Java olduğunda geçerlidir.) |
