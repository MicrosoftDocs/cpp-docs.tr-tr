---
description: Daha fazla bilgi için bkz. Android hata ayıklayıcısı özellikleri
title: Android hata ayıklayıcısı özellikleri (C++)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 27068b56421860b1e77b6cacf7e2ef4fae147a24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136532"
---
# <a name="android-debugger-properties"></a>Android hata ayıklayıcı özellikleri

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Hata ayıklayıcı türü | Hata ayıklamanın hangi kod türünde olduğunu belirtir. | **Yalnızca yerel**<br /><br />**Yalnızca Java** |
| Hata ayıklama hedefi | Hata ayıklama için kullanılacak öykünücüyü veya cihazı belirtir. Hiçbir öykünücü çalışmıyorsa, bir cihazı başlatmak için ' Android sanal cihazı (AVD) Yöneticisi ' ni kullanın. |
| Başlatılacak paket | Hata ayıklaması yapılacak *. apk* konumunu belirtir. Bu seçenek, uygulamanın hatası ayıklandığında paketi (APK) başlatır. |
| Başlatma etkinliği | Uygulamayı başlatmak için kullanılacak Android etkinliği, bildirimde kullanılan bir ile eşleşmelidir. Listeyi *AndroidManifest.xml* almak ve dinamik olarak doldurmak için Uygula ' ya basın. |
| Ek sembol arama yolları | Hata ayıklama sembolleri için ek arama yolu. |
| Ek Java kaynağı arama yolları | Java kaynak dosyaları için ek arama yolları. (Yalnızca hata ayıklayıcı türü yalnızca Java olduğunda geçerlidir.) |
