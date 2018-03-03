---
title: "Dosyalar ve akışlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- files [C++]
- streams
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0285d8395b5a135ac75c40914232ad820f36f00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="files-and-streams"></a>Dosyalar ve Akışlar
Bir program, okuma ve dosyalara yazma, hedef ortam ile iletişim kurar. Bir dosya olabilir:  
  
-   Veri okuma ve yazma sürekli olarak ayarlayın.  
  
-   Bir program (örneğin, bir işlem hattı) tarafından oluşturulan bayt akışı.  
  
-   Bayt akışı bir aygıttaki gönderilen veya alınan.  
  
 Son iki öğeleri etkileşimli dosyalarıdır. Genellikle, bir programla etkileşim kurmasına asıl yollarla dosyalarıdır. Tüm bu tür dosyaları çok aynı şekilde işlemek — kitaplık işlevleri çağırarak. Standart üstbilgi STDIO içerir. Bu işlevlerin çoğu bildirmek için H.  
  
 Birçok dosyada işlemleri gerçekleştirmek için önce dosyayı açılması gerekir. Bir dosyanın açılması çeşitli dosyalar arasında çok sayıda fark üzerinden glosses standart C Kitaplığı veri yapısında bir akış ile ilişkilendirir. Kitaplık her dosya türünde bir nesne akışında durumunu korur.  
  
 Hedef ortam program başlatma önce üç dosyaları açar. Kitaplık işlevini çağırarak bir dosyayı açabilmek için [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) iki bağımsız değişkenlere sahip. ( `fopen` İşlevi kullanım dışı bırakıldı, kullanın [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) yerine.) İlk bağımsız değişkeni bir dosya adıdır. İkinci bağımsız değişkeni belirten bir C dizesidir:  
  
-   Olup, ya da her ikisine veri dosyasından veri okunamıyor veya yazılamıyor düşündüğünüz.  
  
-   Dosya için yeni içerik oluştur (veya daha önce yoktu, bir dosya oluşturmak) düşündüğünüz veya varolan içeriğini bırakın.  
  
-   Dosyaya yazma varolan içeriği değiştirebilirsiniz olup yalnızca dosyanın sonunda bayt eklemeniz gerekir.  
  
-   Bir metin akış ya da bir ikili akış değiştirmek isteyip istemediğinizi.  
  
 Dosya başarıyla açıldıktan sonra ardından akış odaklı bayt (bayt akışı) olup olmadığını belirlemek veya geniş (geniş bir akışı) yönelik. Bir akış başlangıçta bağlanmamış. Akışta çalışması için bazı işlevlerini çağırma yönelik belirli diğer işlevleri yönelik geniş bir bunu yaparken bayt kolaylaştırır. Bir çağrı tarafından kapatılana kadar kez kurulduğunda, bir akış yönünü tutar [fclose](../c-runtime-library/reference/fclose-fcloseall.md) veya [freopen](../c-runtime-library/reference/freopen-wfreopen.md).  
  
 © 1989-2001 tarafından hazırlanan Plauger ve Jim Brodie. Tüm hakları saklıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin ve ikili akışlar](../c-runtime-library/text-and-binary-streams.md)   
 [Bayt ve geniş akışlar](../c-runtime-library/byte-and-wide-streams.md)   
 [Akışları denetleme](../c-runtime-library/controlling-streams.md)   
 [Akış Durumları](../c-runtime-library/stream-states.md)