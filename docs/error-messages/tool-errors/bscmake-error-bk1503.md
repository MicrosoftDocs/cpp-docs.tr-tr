---
title: BSCMAKE Hatası BK1503
ms.date: 11/04/2016
f1_keywords:
- BK1503
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
ms.openlocfilehash: 2c8ca005922c3c94b557e2f1052e8811099d9948
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555814"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE Hatası BK1503

'filename' dosyasına yazılamıyor [: neden]

Bir tarayıcı veritabanına derleme sırasında oluşturulan .sbr dosyaları BSCMAKE birleştirir. Sonuçta elde edilen tarayıcı veritabanı 64 MB'ı aşarsa veya 4092 giriş (.sbr) dosyalarının sayısını aşarsa, bu hata yayılan.

Sorun birden fazla 4092 .sbr dosyaları tarafından neden oluyorsa, giriş dosyalarının sayısını azaltmanız gerekir. Visual Studio içinden bu tarafından gerçekleştirilebilir [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) rojeyi sonra dosyası tarafından temelinde tekrar kontrol edin.

.Bsc dosyası 64 MB'tan büyük sorun nedeniyle, giriş olarak .sbr dosyaları sayısını azaltmayı elde edilen .bsc dosyası boyutunu azaltın. Ayrıca, göz atma bilgisi miktarı /Em (makro genişletilmiş semboller hariç), /El (yerel değişkenler hariç) ve /Es (sistem dosyaları hariç) kullanılarak azaltılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[BSCMAKE Seçenekleri](../../build/reference/bscmake-options.md)