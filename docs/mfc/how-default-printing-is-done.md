---
title: "Varsayılan yazdırmayı yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5001026f1e5fe9e1fed86a49b0565b09ddd6b555
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-default-printing-is-done"></a>Varsayılan Yazdırmayı Yapma
Bu makalede Windows varsayılan yazdırma işlemi MFC çerçevesi bakımından açıklanmaktadır.  
  
 MFC uygulamalarında görünüm sınıfı adlı bir üye işlevi sahip `OnDraw` , tüm çizim kodunu içerir. `OnDraw`bir işaretçi geçen bir [CDC](../mfc/reference/cdc-class.md) nesnesini parametre olarak. Olduğunu `CDC` nesnesi tarafından üretilen görüntü almak için cihaz bağlamı temsil eder `OnDraw`. Belge görüntüleme penceresi zaman alan bir [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) iletisi, framework çağrıları `OnDraw` ve cihaz bağlamı ekranın geçirir (bir [CPaintDC](../mfc/reference/cpaintdc-class.md) belirli nesnesi). Buna göre `OnDraw`gider çıkışını ekranına.  
  
 Windows için programlamada yazıcıya gönderen çıkış ekranına Çıkış göndermeyi çok benzer. Windows grafik cihaz arabirimi (GDI) donanımdan bağımsız olmasıdır. Uygun cihaz bağlamı kullanarak, yazdırma veya ekran görüntüsü için aynı GDI işlevleri kullanabilirsiniz. Varsa `CDC` nesnesinin `OnDraw` alır yazıcı temsil eden `OnDraw`gider çıkışını yazıcı.  
  
 Bu ek çaba yapmanıza gerek kalmadan MFC uygulamaları basit yazdırma nasıl gerçekleştirebileceğiniz açıklanmaktadır. Framework Yazdır iletişim kutusunu görüntüleme ve yazıcı için bir cihaz bağlamı oluşturma ilgilenir. Kullanıcı Dosya menüsünden Yazdır komutunu seçtiğinde, görünüm bu cihaz bağlamına geçirir `OnDraw`, yazıcıda belge çizer.  
  
 Ancak, yazdırma ve ekran görüntüsü arasında önemli bazı farklar vardır. Yazdırma sırasında farklı sayfaları ve bunları birer birer, hangi kısmını görüntülemek yerine görünür bir penceresinde görünen belge bölmek gerekir. Bir corollary (harf boyutu, geçerli boyut veya Zarf olup) kağıt boyutunu farkında olmanız gerekir. Yatay veya dikey modu gibi farklı yönleri yazdırma isteyebilirsiniz. Microsoft Foundation Class Kitaplığı, bu yetenekleri eklemek bir protokol sağlar böylece uygulamanız bu sorunların nasıl işleyeceğini tahmin edilemez.  
  
 Protokol makalesinde açıklanan [çok sayfalı belgeleri](../mfc/multipage-documents.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma](../mfc/printing.md)

