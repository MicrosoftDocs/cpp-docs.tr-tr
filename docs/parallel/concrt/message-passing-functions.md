---
title: "İleti geçirme işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4139068c8871fe69f43168fe925011a48411a74b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
-   [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Nasıl yapılır: çeşitli üretici-tüketici desenlerini uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [Nasıl yapılır: call ve transformer sınıflarına iş işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [Nasıl yapılır: veri ardışık düzeninde transformer kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [Nasıl yapılır: Tamamlanan görevler arasında seçim](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [Nasıl yapılır: düzenli aralıkla ileti gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [Nasıl yapılır: ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send işlevi](reference/concurrency-namespace-functions.md#send)   
 [asend işlevi](reference/concurrency-namespace-functions.md#asend)   
 [receive işlevi](reference/concurrency-namespace-functions.md#receive)   
 [try_receive işlevi](reference/concurrency-namespace-functions.md#try_receive)


