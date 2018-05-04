---
title: Metin ve ikili akışlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- binary streams
- text streams
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e91881f738c1b6411179c4f8e10e30f69e7b8667
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="text-and-binary-streams"></a>Metin ve İkili Akışlar
Bir metin akış metin odaklı bir görüntüye yazılabilir ve böylece okunabilir hale metnin bir veya daha fazla satırlardan oluşur. Bir metin akışından okuma bulunduğunda program okur bir `NL` (yeni satır) her satırın sonundaki. Bir metin akış yazarken, program Yazar bir `NL` bir satırın sonuna sinyal. Metin dosyalarını olarak temsil etmek için hedef ortamlar arasında farklı kuralları eşleştirmek için kitaplık işlevleri sayısı ve program ve bir metin akış arasında aktarılan karakterlerinin gösterimlerini değiştirebilirsiniz.  
  
 Bu nedenle, bir metin akış içinde konumlandırma sınırlıdır. Geçerli dosya konumu göstergesi çağırarak elde edebileceğiniz [fgetpos](../c-runtime-library/reference/fgetpos.md) veya [ftell](../c-runtime-library/reference/ftell-ftelli64.md). Çağırarak bu şekilde elde konumunda ya da başlangıcında veya akışın sonuna bir metin akış yerleştirebilirsiniz [fsetpos](../c-runtime-library/reference/fsetpos.md) veya [fseek](../c-runtime-library/reference/fseek-fseeki64.md). Herhangi bir değişiklik konumunun iyi desteklenmiyor olabilir.  
  
 En fazla taşınabilirlik için program yazamaz:  
  
-   Boş dosyalar.  
  
-   Bir satır sonunda boşluk karakterleri.  
  
-   Kısmi satırlar (atlama tarafından `NL` bir dosya sonunda).  
  
-   NL, yazdırılabilir karakterleri dışında karakterler ve `HT` (yatay sekme).  
  
 Bu kurallar izlerseniz, (ya da bayt veya birden çok baytlı karakterler) bir metin akışından okuma karakter dizisi dosyasını oluştururken metin akışına yazdı karakter dizisi ile eşleşir. Aksi takdirde, kitaplık işlevleri kapatıldığında dosya boşsa, oluşturduğunuz dosya kaldırabilirsiniz. Veya alter veya dosyaya yazmak karakterleri silin.  
  
 Bir ikili akış rasgele bilgilerinin bir veya daha fazla bayt oluşur. Rastgele bir nesne (bayt yönelimli) ikili akış depolanan değer yazma ve yazdığınız zaman tam olarak ne nesnesinde depolanan okuyun. Kitaplık işlevleri program ve ikili akış arasında iletme bayt değiştirmeyin. Bunlar ancak, rasgele bir null bayt sayısı olan ikili bir akış yazmak dosyasına ekleyebilirsiniz. Program, bu ek boş bayt ikili akış sonunda uğraşmanız gerekir.  
  
 Bu nedenle, bir ikili akış içinde konumlandırma akışın sonuna göre konumlandırma dışında iyi tanımlanmış. Alın ve geçerli dosya konumu göstergesi bir metin akış aynı alter. Ayrıca, tarafından kullanılan uzaklıkları [ftell](../c-runtime-library/reference/ftell-ftelli64.md) ve [fseek](../c-runtime-library/reference/fseek-fseeki64.md) (bayt sıfır olan) akış başından itibaren bayt sayısı tamsayı üzerinde bu uzaklıkları aritmetik tahmin edilebilir sonuçlar verir şekilde.  
  
 Bir bayt akış dosya bir bayt dizisi değerlendirir. Programında, akış aynı yukarıda açıklanan olası değişiklikleri dışında bayt dizisi gibi görünüyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyalar ve Akışlar](../c-runtime-library/files-and-streams.md)