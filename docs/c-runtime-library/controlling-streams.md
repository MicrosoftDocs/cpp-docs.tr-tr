---
title: Akışları denetleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- Controlling Streams
dev_langs:
- C++
helpviewer_keywords:
- streams, controlling
- controlling streams
- streams
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2cb0d049cceba82a7812c3b676c6955c433b439
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="controlling-streams"></a>Akışları Denetleme
[fopen](../c-runtime-library/reference/fopen-wfopen.md) türünde bir nesne adresini döndürür `FILE`. Bu adresi olarak kullanın `stream` açık bir dosyayı çeşitli işlemleri gerçekleştirmek için çeşitli kitaplığı işlevlerinin bağımsız değişkeni. Her karakteri çağırarak salt okunur ise gibi bir bayt akış için tüm giriş gerçekleşir [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), ve her bir karakteri çağırarak gibi yazılmışsa tüm çıktı gerçekleşir [fputc](../c-runtime-library/reference/fputc-fputwc.md). Her karakteri çağırarak salt okunur ise gibi geniş bir akış için tüm giriş gerçekleşir [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), ve her bir karakteri çağırarak gibi yazılmışsa tüm çıktı gerçekleşir [fputwc](../c-runtime-library/reference/fputc-fputwc.md).  
  
 Bir dosya çağırarak kapatabilirsiniz [fclose](../c-runtime-library/reference/fclose-fcloseall.md), sonrasında adresini `FILE` nesnesi geçersiz.  
  
 A `FILE` nesne depolayan bir akış durumu da dahil olmak üzere:  
  
-   Bir hata göstergesi okuma karşılaştığı bir işlev tarafından sıfır olmayan ayarlayın veya yazma hatası.  
  
-   Bir dosya sonu göstergesi okurken dosyasının sonuna karşılaştığı bir işlev tarafından sıfır olmayan ayarlayın.  
  
-   Dosya konumlandırma istekleri destekliyorsa bir dosya konumu göstergesi sonraki bayt okuma veya yazma, akışta belirtir.  
  
-   A [akış durumu](../c-runtime-library/stream-states.md) akış okur ve/veya yazma ve akış ilişkisiz olduğunu kabul eder olup olmadığını bayt yönelik veya geniş yönelik belirtir.  
  
-   Bir dönüştürme durumu herhangi biri kısmen birleştirilmiş veya oluşturulan durumunu herhangi bir dizi için shift durum dosyasındaki bayt yanı sıra birden çok baytlı karakter genelleştirilmiş hatırlıyor).  
  
-   Bir dosyayı arabelleğe adresini ve kitaplık işlevleri okuma performansını artırmak ve akışına yazma işlemleri için kullanabileceğiniz bir dizi nesnesi boyutunu belirtir.  
  
 Depolanan herhangi bir değer değiştirmeyin bir `FILE` nesne veya o nesne ile kullanmak için belirttiğiniz dosya arabelleği. Kopyalama yapılamıyor bir `FILE` nesne ve temelinizi kopya olarak adresini kullanın bir `stream` kitaplığı işlevi bağımsız değişken.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyalar ve Akışlar](../c-runtime-library/files-and-streams.md)