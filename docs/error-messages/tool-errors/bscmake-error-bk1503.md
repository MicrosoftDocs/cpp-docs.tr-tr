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
ms.openlocfilehash: 06d4a05a8f2d04c3f8a991d4444b35295408a7b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE Hatası BK1503
'filename' dosyasına yazılamıyor [: neden]  
  
 BSCMAKE bir tarayıcı veritabanına derleme sırasında oluşturulan .sbr dosyaları birleştirir. Sonuçta elde edilen tarayıcı veritabanı 64 MB aşarsa veya 4092 giriş (.sbr) dosyalarının sayısını aşarsa, bu hata yayılan.  
  
 Birden fazla 4092 .sbr dosyaları tarafından soruna neden olursa, giriş dosyaları sayısını azaltın gerekir. Gelen Visual Studio içinde bu tarafından gerçekleştirilebilir [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) tüm proje sonra dosyası tarafından temelinde yeniden denetleme.  
  
 .Bsc dosyası 64 MB'den büyük sorun nedeniyle, sayısını .sbr dosyaları giriş olarak elde edilen .bsc dosyası boyutunu azaltın. Ayrıca, Gözat bilgi miktarını /Em (makrosu genişletilmiş simge hariç), /El (yerel değişkenler hariç) ve /Es (sistem dosyaları hariç) kullanılarak azaltılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BSCMAKE Seçenekleri](../../build/reference/bscmake-options.md)