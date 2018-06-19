---
title: BSCMAKE nasıl derler bir. BSC dosya | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cdc8a2840e3beb1272b33b2794f70a979684f46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373494"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE .Bsc Dosyasını Nasıl Derler
BSCMAKE oluşturur veya bunu en verimli şekilde .bsc dosyası oluşturur. Olası sorunları önlemek için yapılandırma işlemi anlamak önemlidir.  
  
 BSCMAKE gözatma bilgileri dosyası oluşturduğunda, uzunluğu sıfır olarak .sbr dosyaları tamsayıya dönüştürür. Aynı dosyanın sonraki derleme sırasında sıfır uzunluklu (veya boş) .sbr dosyası BSCMAKE .sbr dosyası yapmak için hiçbir yeni katkı olduğunu bildirir. Bir güncelleştirme dosyasının bu bölümü gerekli değildir ve artımlı derleme yeterli olacaktır bilmeniz BSCMAKE sağlar. Her derleme sırasında (/n seçeneği belirtilmediği sürece), BSCMAKE ilk kez girişimlerini değişen .sbr dosyaları kullanarak dosya artımlı olarak güncelleştirmenizi.  
  
 BSCMAKE /o seçeneğiyle belirtilen ada sahip bir .bsc dosyasını arar. /O belirtilmezse, BSCMAKE için ilk .sbr dosyası ve .bsc uzantılı bir taban adına sahip bir dosya arar. Dosya varsa, yalnızca katkıda bulunan .sbr dosyaları kullanarak gözatma bilgileri dosyası, artımlı bir yapı BSCMAKE gerçekleştirir. Dosya mevcut değilse BSCMAKE tüm .sbr dosyaları kullanarak tam bir yapı gerçekleştirir. Yapılar için kurallar aşağıdaki gibidir:  
  
-   Başarılı olması tam derleme için tüm .sbr dosyaları bulunmalı ve değil kısaltılması gerekir belirtildi. .Sbr dosyası kesilirse, onu (yeniden derlenmesi veya birleştirme) BSCMAKE çalıştırmadan önce yeniden oluşturmanız gerekir.  
  
-   Bir artımlı derleme için başarılı olması .bsc dosyası mevcut olması gerekir. Tüm katkıda bulunan .sbr dosyaları, boş dosyalar bile bulunmalı ve BSCMAKE komut satırında belirtilmesi gerekir. BSCMAKE komut satırından .sbr dosyası atlarsanız, kendi katkı dosyasından kaldırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.Bsc Dosyası Derleme](../../build/reference/building-a-dot-bsc-file.md)