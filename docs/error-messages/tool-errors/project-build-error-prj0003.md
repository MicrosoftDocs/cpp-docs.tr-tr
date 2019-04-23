---
title: Proje Derleme Hatası PRJ0003
ms.date: 11/04/2016
f1_keywords:
- PRJ0003
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
ms.openlocfilehash: 00d101e62d49078ebfcfff9455497f30224b84fe
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039526"
---
# <a name="project-build-error-prj0003"></a>Proje Derleme Hatası PRJ0003

> Hata UNICODE '*komut satırı*'.

*Komut satırı* komut biçimlendirilmiş girişinde gelen **özellik sayfaları** iletişim kutusu, bir hata kodu döndürdü, ancak içinde hiçbir bilgi görünmüyor **çıkış** penceresi.

Bu hata için olası nedenler şunlardır:

- Projenize ATL sunucu üzerinde bağlıdır. Visual Studio 2008'de başlayarak, ATL Sunucu artık Visual Studio'nun bir parçası olarak dahil edilir, ancak CodePlex projesi bir paylaşılan kaynak olarak yayımlanmıştır. ATL Sunucu kaynak kodu ve Araçları'nı indirmek için Git [ATL Sunucu kitaplığının ve araçları](http://go.microsoft.com/fwlink/p/?linkid=81979).

- Düşük sistem kaynakları. Bu sorunu çözmek için bazı uygulamaları kapatın.

- Yeterli güvenlik ayrıcalıkları. Yeterli ayrıcalıklara sahip olduğunuzu doğrulayın.

- Belirtilen çalıştırılabilir yolu **VC ++ dizinleri** çalıştırmayı denediğiniz araç için yolu içermiyor. Bilgi için [derleyici ayarlayın ve derleme özellikleri](../../build/working-with-project-properties.md)

- Derleme görevleri dosyası projeleri için üzerinde çalışacak bir komut eksik **derleme komut satırı** veya **yeniden komut satırı**.

## <a name="see-also"></a>Ayrıca bkz.

[Proje Derleme Hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)