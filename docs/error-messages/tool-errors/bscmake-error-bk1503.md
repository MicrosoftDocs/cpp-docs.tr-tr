---
title: BSCMAKE hatası BK1503 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1503
dev_langs:
- C++
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16bf228804cb24f4fe7a2428dc581116d4cec91d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064681"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE Hatası BK1503

'filename' dosyasına yazılamıyor [: neden]

Bir tarayıcı veritabanına derleme sırasında oluşturulan .sbr dosyaları BSCMAKE birleştirir. Sonuçta elde edilen tarayıcı veritabanı 64 MB'ı aşarsa veya 4092 giriş (.sbr) dosyalarının sayısını aşarsa, bu hata yayılan.

Sorun birden fazla 4092 .sbr dosyaları tarafından neden oluyorsa, giriş dosyalarının sayısını azaltmanız gerekir. Visual Studio içinden bu tarafından gerçekleştirilebilir [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) rojeyi sonra dosyası tarafından temelinde tekrar kontrol edin.

.Bsc dosyası 64 MB'tan büyük sorun nedeniyle, giriş olarak .sbr dosyaları sayısını azaltmayı elde edilen .bsc dosyası boyutunu azaltın. Ayrıca, göz atma bilgisi miktarı /Em (makro genişletilmiş semboller hariç), /El (yerel değişkenler hariç) ve /Es (sistem dosyaları hariç) kullanılarak azaltılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[BSCMAKE Seçenekleri](../../build/reference/bscmake-options.md)