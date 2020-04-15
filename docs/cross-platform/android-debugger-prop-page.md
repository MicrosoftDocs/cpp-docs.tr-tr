---
title: Android Hata Ayıklama Özellikleri (C++)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 23fd871f030593607cf374870b96e09d8bc2da7a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374209"
---
# <a name="android-debugger-properties"></a>Android hata ayıklama özellikleri

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Hata Ayıklama Türü | Hata ayıklamak için hangi kod türünü belirtir. | **Yalnızca Yerel**<br /><br />**Yalnızca Java** |
| Hata Ayıklama Hedefi | Hata ayıklama için kullanılacak emülatör veya aygıtı belirtir. Hiçbir emülatör çalışıyorsa, bir aygıtı başlatmak için 'Android Sanal Aygıt (AVD) Yöneticisi'ni kullanın. |
| Başlatılan Paket | Debugged olacak *.apk* konumunu belirtir. Bu seçenek, uygulama debugged olduğunda Paket (APK) başlar. |
| Fırlatma Etkinliği | Uygulamayı başlatmak için kullanmak için Android etkinliği, manifestoda kullanılan bir maç zorundadır. Listeyi *AndroidManifest.xml'den* almak ve dinamik olarak doldurmak için Uygula'ya basın. |
| Ek Sembol Arama Yolları | Hata ayıklama sembolleri için ek arama yolu. |
| Ek Java Kaynak Arama Yolları | Java kaynak dosyaları için ek arama yolları. (Yalnızca Hata Ayıklama Türü Yalnızca Java olduğunda geçerlidir.) |
