---
description: 'Hakkında daha fazla bilgi edinin: proje derleme hatası PRJ0003'
title: Proje Derleme Hatası PRJ0003
ms.date: 11/04/2016
f1_keywords:
- PRJ0003
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
ms.openlocfilehash: cefd56e1d11da77f288333fb0e1f9c10ef684d12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119414"
---
# <a name="project-build-error-prj0003"></a>Proje Derleme Hatası PRJ0003

> '*Komut satırı*' üretilirken hata oluştu.

**Özellik sayfaları** iletişim kutusundaki girişten oluşturulan *komut satırı* komutu bir hata kodu döndürdü, ancak **Çıkış** penceresinde bilgi görünmüyor.

Bu hatanın olası nedenleri şunlardır:

- Projeniz ATL sunucusuna bağlıdır. Visual Studio 2008 ' den başlayarak, ATL Server artık Visual Studio 'nun bir parçası olarak dahil değildir, ancak CodePlex 'te paylaşılan kaynak proje olarak yayımlanmıştır. ATL sunucusu kaynak kodunu ve araçlarını indirmek için, [ATL sunucu kitaplığı ve araçları](https://go.microsoft.com/fwlink/p/?linkid=81979)' na gidin.

- Düşük sistem kaynakları. Bu sorunu çözmek için bazı uygulamaları kapatın.

- Yetersiz güvenlik ayrıcalıkları. Yeterli güvenlik ayrıcalıklarına sahip olduğunuzu doğrulayın.

- **VC + + dizinlerinde** belirtilen yürütülebilir yollar, çalıştırmayı denediğiniz aracın yolunu içermez. Bilgi için bkz. [derleyici ve derleme özelliklerini ayarlama](../../build/working-with-project-properties.md)

- Derleme görevleri dosyası projeleri için, **derleme komut satırı** veya **yeniden oluşturma komut satırı** üzerinde çalıştırılacak bir komutun eksik olması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Proje derleme hataları ve uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
