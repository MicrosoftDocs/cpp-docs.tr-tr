---
title: "BSCMAKE hatası BK1503 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1503
dev_langs: C++
helpviewer_keywords: BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86f2b6d282857409cdb1e1d49e04775e9886cde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE Hatası BK1503
'filename' dosyasına yazılamıyor [: neden]  
  
 BSCMAKE bir tarayıcı veritabanına derleme sırasında oluşturulan .sbr dosyaları birleştirir. Sonuçta elde edilen tarayıcı veritabanı 64 MB aşarsa veya 4092 giriş (.sbr) dosyalarının sayısını aşarsa, bu hata yayılan.  
  
 Birden fazla 4092 .sbr dosyaları tarafından soruna neden olursa, giriş dosyaları sayısını azaltın gerekir. Gelen Visual Studio içinde bu tarafından gerçekleştirilebilir [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) tüm proje sonra dosyası tarafından temelinde yeniden denetleme.  
  
 .Bsc dosyası 64 MB'den büyük sorun nedeniyle, sayısını .sbr dosyaları giriş olarak elde edilen .bsc dosyası boyutunu azaltın. Ayrıca, Gözat bilgi miktarını /Em (makrosu genişletilmiş simge hariç), /El (yerel değişkenler hariç) ve /Es (sistem dosyaları hariç) kullanılarak azaltılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BSCMAKE Seçenekleri](../../build/reference/bscmake-options.md)