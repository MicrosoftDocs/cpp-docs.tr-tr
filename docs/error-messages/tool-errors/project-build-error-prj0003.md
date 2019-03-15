---
title: Proje Derleme Hatası PRJ0003
ms.date: 11/04/2016
f1_keywords:
- PRJ0003
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
ms.openlocfilehash: a6530045870573921cf626ceeec4c1dca10cdbfb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816184"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Proje Derleme Hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)