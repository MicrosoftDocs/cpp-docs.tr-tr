---
title: "Bağlayıcı araçları hatası LNK1211 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1211
dev_langs: C++
helpviewer_keywords: LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c0fd4ac4ae616d256d3d5971fe417dcf7846b4ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1211"></a>Bağlayıcı Araçları Hatası LNK1211
önceden derlenmiş türü bilgileri; bulunamadı 'filename' bağlantılı veya üzerine değil  
  
 İle derlenmiş belirli nesne dosyası [/Yc](../../build/reference/yc-create-precompiled-header-file.md), bağlantı komutunda belirtilmedi veya yazıldı.  
  
 Önceden derlenmiş üst bilgileri kullanan bir hata ayıklama kitaplığı oluşturuyorsanız ve /Yc belirtirseniz ve [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C++ hata ayıklama bilgileri CodeView içeren önceden derlenmiş nesnesi dosyası oluşturur. Yalnızca zaman, önceden derlenmiş nesne dosyası kitaplıkta depolamasına oluşur, yürütülebilir bir görüntü oluşturmak için kitaplığı kullanmasına ve başvurulan nesne dosyaları hiçbir geçişli önceden derlenmiş nesne dosyası tanımlar işlevleri hiçbirini başvuran.  
  
 Bu durumu çözmek için iki yöntem vardır:  
  
-   Belirtin [/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) CodeView bilgileri önceden derlenmiş başlığından her nesne modül eklemek için derleyici seçeneği. Genellikle uygulama bağlamak için gereken süreyi artırabilir büyük nesne modülleri oluşturduğundan bu yöntem daha az tercih edilir.  
  
-   Belirtin [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) ve herhangi bir işlev tanımları içermeyen bir önceden derlenmiş üst bilgi dosyası oluşturduğunuzda herhangi bir rastgele dize adını geçirin. Önceden derlenmiş nesne dosyasında bir simge oluşturmak ve bu simgeyi önceden derlenmiş nesne dosyasıyla ilişkili önceden derlenmiş üst bilgi dosyası kullanılan her bir nesne dosyadaki başvuru yayma için derleyici yönlendirir.  
  
 Derleme zaman sahip bir modül **/Yc** ve **/Yl**, derleyici benzer bir simge oluşturur `__@@_PchSym_@00@...@symbol_name`, burada üç nokta (...) derleyicinin ürettiği karakter dizesini temsil eder ve depolar Nesne Modül. Bu önceden derlenmiş üst bilgi ile derleme herhangi bir kaynak dosyayı nesne modülü ve kitaplık hata ayıklama bilgilerini içerecek şekilde bağlayıcı neden olan belirtilen simgeyi gösterir.  
  
 Bilgi Bankası makalesi Q102697 sorun bu hata hakkında daha fazla bilgi için bkz: derleme hataları kullanarak önceden derlenmiş üst bilgisinde hata ayıklama kitaplığı.