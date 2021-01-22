---
description: Kendi gecikme yük Yardımcısı işlevinizi geliştirme hakkında daha fazla bilgi edinin
title: Kendi gecikme yük Yardımcısı işlevinizi geliştirme
ms.date: 01/19/2021
helpviewer_keywords:
- helper functions
ms.openlocfilehash: 2845a426023ed8b5e2bcfb0056c9be6b829dd23a
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667439"
---
# <a name="develop-your-own-delay-load-helper-function"></a>Kendi gecikme yük Yardımcısı işlevinizi geliştirme

Gecikme yükü Yardımcısı yordamının kendi sürümünüzü sağlamak isteyebilirsiniz. Kendi yordamınıza, DLL veya içeri aktarmalar adına göre belirli işlemleri yapabilirsiniz. Kendi kodunuzu eklemenin iki yolu vardır: kendi yardımcı işlevinizi, büyük olasılıkla sağlanan koda göre kodlayın. Ya da, [bildirim kancalarını](notification-hooks.md)kullanarak kendi işlevinizi çağırmak için sağlanan yardımcıyı kanca.

## <a name="code-your-own-helper"></a>Kendi yardımcınızın kodunu yapın

Kendi yardımcı yordamınızın oluşturulması basittir. Mevcut kodu, yeni işleviniz için bir kılavuz olarak kullanabilirsiniz. İşlevinizin mevcut yardımcı ile aynı çağırma kurallarını kullanması gerekir. Ve bağlayıcı tarafından oluşturulan dönüştürücüler döndürürse, uygun bir işlev işaretçisi döndürmelidir. Kodunuzu oluşturduktan sonra, aramayı karşıya da çağrmış olabilirsiniz.

## <a name="use-the-start-processing-notification-hook"></a>İşlemi Başlat bildirim kancasını kullan

Bildirimin varsayılan Yardımcısı ile aynı değerleri alan Kullanıcı tarafından sağlanan bir bildirim kanca işlevine yeni bir işaretçi sağlamak büyük olasılıkla en kolay yoldur `dliStartProcessing` . Bu noktada, varsayılan yardımcıya başarılı bir geri dönme varsayılan yardımdaki tüm diğer işlemleri atladığı için kanca işlevi aslında yeni yardımcı işlev haline gelebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
