---
title: Kendi yardımcı işlevinizi geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d95434c51bdfca07e48714c8c1e13bcdb64dc02f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716007"
---
# <a name="developing-your-own-helper-function"></a>Kendi Yardımcı İşlevinizi Geliştirme

DLL içeri aktarmaları ve adlarına göre belirli işleme yapmak için yordamının kendi sürüm sağlamak isteyebilirsiniz. Bunu yapmanın iki yöntemi vardır: büyük olasılıkla sağlanan kodu, göre kendi kodlama veya yalnızca daha önce ayrıntılı bildirim kancaları kullanarak sağlanan sürüm takma.

## <a name="code-your-own"></a>Kendi kod

Temelde girilen kod bir kılavuz olarak yeni bir tane için kullanabileceğiniz bu yana oldukça basittir. Elbette, çağırma kurallarına uyması gerekir ve bağlayıcı tarafından oluşturulan dönüştürücülerine döndürürse, doğru işlev işaretçisi döndürmelidir. Bir kez kodunuzda tarayıcınızdaki alma çağrısı dışında veya çağrı karşılamak için istediğiniz yapabilirsiniz.

## <a name="use-the-start-processing-notification-hook"></a>Bildirim kanca işleme Başlat

Büyük olasılıkla yalnızca yeni bir bildirim dliStartProcessing üzerinde varsayılan yardımcı olarak aynı değerleri alır bildirim kullanıcı tarafından sağlanan bir kanca işlevini işaretçiye sağlamak kolay olacaktır. Bu noktada, başarılı bir geri döndürme varsayılan Yardımcısı için diğer tüm varsayılan yardımcı işleme atlama gibi kanca işlevini temelde yeni yardımcı işlevini dönüşebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)