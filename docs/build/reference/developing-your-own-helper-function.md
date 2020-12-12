---
description: 'Hakkında daha fazla bilgi edinin: kendi yardımcı Işlevinizi geliştirme'
title: Kendi Yardımcı İşlevinizi Geliştirme
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
ms.openlocfilehash: da536d13da9a596c5667c3fa84311b73e66d71ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201462"
---
# <a name="developing-your-own-helper-function"></a>Kendi Yardımcı İşlevinizi Geliştirme

DLL veya içeri aktarmalar adına göre belirli işlemleri yapmak için kendi yordamını sağlamak isteyebilirsiniz. Bunu yapmanın iki yöntemi vardır: kendi kodunuzu kodlayın, büyük olasılıkla sağlanan koda göre veya yalnızca daha önce ayrıntılı bildirim kancalarını kullanarak sağlanan sürümü kullanıma alınıyor.

## <a name="code-your-own"></a>Kendi kodunuzu kodlayın

Bu oldukça basittir çünkü temel olarak sağlanan kodu yeni bir kılavuz olarak kullanabilirsiniz. Kuşkusuz, çağrı kurallarına uyması gerekir ve bağlayıcı tarafından oluşturulan dönüştürücüler öğesine dönerse, uygun bir işlev işaretçisi döndürmelidir. Kodunuzda bir kez, çağrıyı karşılamak veya çağrıdan ulaşmak için istediğiniz kadar çok şey yapabilirsiniz.

## <a name="use-the-start-processing-notification-hook"></a>Işlemi Başlat bildirim kancasını kullan

Bir kullanıcı tarafından sağlanan bildirim kanca işlevine, bildirim dliStartProcessing varsayılan Yardımcısı ile aynı değerleri alan yeni bir işaretçi sağlamak büyük olasılıkla en kolay hale gelir. Bu noktada, varsayılan yardımcıya başarılı bir geri dönme varsayılan yardımdaki tüm işlemleri atlayacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
