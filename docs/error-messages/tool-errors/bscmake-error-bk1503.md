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
ms.openlocfilehash: c75e8513ead68befe2ca4ecd22475dc0a9071431
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE Hatası BK1503
'filename' dosyasına yazılamıyor [: neden]  
  
 BSCMAKE bir tarayıcı veritabanına derleme sırasında oluşturulan .sbr dosyaları birleştirir. Sonuçta elde edilen tarayıcı veritabanı 64 MB aşarsa veya 4092 giriş (.sbr) dosyalarının sayısını aşarsa, bu hata yayılan.  
  
 Birden fazla 4092 .sbr dosyaları tarafından soruna neden olursa, giriş dosyaları sayısını azaltın gerekir. Gelen Visual Studio içinde bu tarafından gerçekleştirilebilir [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) tüm proje sonra dosyası tarafından temelinde yeniden denetleme.  
  
 .Bsc dosyası 64 MB'den büyük sorun nedeniyle, sayısını .sbr dosyaları giriş olarak elde edilen .bsc dosyası boyutunu azaltın. Ayrıca, Gözat bilgi miktarını /Em (makrosu genişletilmiş simge hariç), /El (yerel değişkenler hariç) ve /Es (sistem dosyaları hariç) kullanılarak azaltılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BSCMAKE seçenekleri](../../build/reference/bscmake-options.md)