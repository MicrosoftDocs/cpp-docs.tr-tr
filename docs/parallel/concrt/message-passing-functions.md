---
title: "İleti geçirme işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9c2daa3f34ba4e73b28e11241d0f64680851fcc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-passing-functions"></a>İleti Geçirme İşlevleri
Zaman uyumsuz aracılar Kitaplığı bileşenleri arasında ileti geçirmenize olanak tanıyan çeşitli işlevleri sağlar.  
  
 Bu ileti geçirme işlevleri, çeşitli ileti bloğu türleriyle kullanılır. Eşzamanlılık Çalışma zamanı tarafından tanımlanan ileti bloğu türleri hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).  
  
##  <a name="top"></a>Bölümler  
 Bu konuda aşağıdaki ileti geçirme işlevleri açıklanmaktadır:  
  
-   [gönderme ve asend](#send)  
  
-   [Alma ve try_receive](#receive)  
  
-   [Örnekler](#examples)  
  
##  <a name="send"></a>gönderme ve asend  

 [Concurrency::send](reference/concurrency-namespace-functions.md#send) işlevi bir iletiyi zaman uyumlu olarak belirtilen hedefe gönderir ve [concurrency::asend](reference/concurrency-namespace-functions.md#asend) işlevi bir ileti zaman uyumsuz olarak belirtilen hedefe gönderir. Hem `send` ve `asend` işlevleri hedef onu sonunda kabul edin veya ileti reddetmek gösterir kadar bekleyin.  
  
 `send` İşlevi, hedef kabul eder ya da onu döndürmeden önce iletiyi reddettiğinde kadar bekler. `send` İşlev döndürür `true` ileti teslim varsa ve `false` Aksi takdirde. Çünkü `send` işlevi çalışır eşzamanlı olarak, `send` işlevi hedef döndürdüğü önce ileti almak bekler.  
  
 Buna karşılık, `asend` işlevi beklememek hedef kabul edebilir veya onu döndürmeden önce iletiyi reddedebilirsiniz. Bunun yerine, `asend` işlev döndürür `true` hedef iletiyi kabul eder ve sonunda sürer. Aksi takdirde, `asend` döndürür `false` hedef ileti reddedildi veya iletisi olup olmadığına dair karar Ertelenen belirtmek için.  
  
 [[Üst](#top)]  
  
##  <a name="receive"></a>Alma ve try_receive  

 [Concurrency::receive](reference/concurrency-namespace-functions.md#receive) ve [concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive) işlevleri, belirli bir kaynaktan veri okuyun. `receive` İşlevi için verileri kullanıma hazır olmasını bekler ancak `try_receive` işlevi hemen döndürür.  
  
 Kullanım `receive` çalışmaya devam etmek için veri sahip olmalıdır. Kullanım `try_receive` işlev geçerli bağlamı engellemelidir değil ya da devam etmek için veri olması gerekmez.  
  
 [[Üst](#top)]  
  
##  <a name="examples"></a>Örnekler  
 Kullanma örnekleri için `send` ve `asend`, ve `receive` İşlevler, aşağıdaki konulara bakın:  
  
-   [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [Nasıl yapılır: Düzenli Aralıkla İleti Gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send işlevi](reference/concurrency-namespace-functions.md#send)   
 [asend işlevi](reference/concurrency-namespace-functions.md#asend)   
 [receive işlevi](reference/concurrency-namespace-functions.md#receive)   
 [try_receive işlevi](reference/concurrency-namespace-functions.md#try_receive)


