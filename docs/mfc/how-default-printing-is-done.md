---
title: Varsayılan yazdırmayı yapma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2cf5b4a9bda3506a9558d5b723020dfe6d43396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358921"
---
# <a name="how-default-printing-is-done"></a>Varsayılan Yazdırmayı Yapma
Bu makalede Windows varsayılan yazdırma işlemi MFC çerçevesi bakımından açıklanmaktadır.  
  
 MFC uygulamalarında görünüm sınıfı adlı bir üye işlevi sahip `OnDraw` , tüm çizim kodunu içerir. `OnDraw` bir işaretçi geçen bir [CDC](../mfc/reference/cdc-class.md) nesnesini parametre olarak. Olduğunu `CDC` nesnesi tarafından üretilen görüntü almak için cihaz bağlamı temsil eder `OnDraw`. Belge görüntüleme penceresi zaman alan bir [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) iletisi, framework çağrıları `OnDraw` ve cihaz bağlamı ekranın geçirir (bir [CPaintDC](../mfc/reference/cpaintdc-class.md) belirli nesnesi). Buna göre `OnDraw`gider çıkışını ekranına.  
  
 Windows için programlamada yazıcıya gönderen çıkış ekranına Çıkış göndermeyi çok benzer. Windows grafik cihaz arabirimi (GDI) donanımdan bağımsız olmasıdır. Uygun cihaz bağlamı kullanarak, yazdırma veya ekran görüntüsü için aynı GDI işlevleri kullanabilirsiniz. Varsa `CDC` nesnesinin `OnDraw` alır yazıcı temsil eden `OnDraw`gider çıkışını yazıcı.  
  
 Bu ek çaba yapmanıza gerek kalmadan MFC uygulamaları basit yazdırma nasıl gerçekleştirebileceğiniz açıklanmaktadır. Framework Yazdır iletişim kutusunu görüntüleme ve yazıcı için bir cihaz bağlamı oluşturma ilgilenir. Kullanıcı Dosya menüsünden Yazdır komutunu seçtiğinde, görünüm bu cihaz bağlamına geçirir `OnDraw`, yazıcıda belge çizer.  
  
 Ancak, yazdırma ve ekran görüntüsü arasında önemli bazı farklar vardır. Yazdırma sırasında farklı sayfaları ve bunları birer birer, hangi kısmını görüntülemek yerine görünür bir penceresinde görünen belge bölmek gerekir. Bir corollary (harf boyutu, geçerli boyut veya Zarf olup) kağıt boyutunu farkında olmanız gerekir. Yatay veya dikey modu gibi farklı yönleri yazdırma isteyebilirsiniz. Microsoft Foundation Class Kitaplığı, bu yetenekleri eklemek bir protokol sağlar böylece uygulamanız bu sorunların nasıl işleyeceğini tahmin edilemez.  
  
 Protokol makalesinde açıklanan [çok sayfalı belgeleri](../mfc/multipage-documents.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma](../mfc/printing.md)

