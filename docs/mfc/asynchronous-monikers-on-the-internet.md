---
title: Internet'teki zaman uyumsuz adlar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b8307b8984ee1b5b6074ee309fdf8a74fe46ea9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asynchronous-monikers-on-the-internet"></a>Internet'teki Zaman Uyumsuz Adlar
Internet uygulama tasarımı için yeni yaklaşımlar nedeniyle, yavaş ağ erişimi gerektirir. Uygulamalar, zaman uyumsuz olarak kullanıcı arabirimi durduruyor önlemek için ağ erişimi gerçekleştirmeniz gerekir. MFC sınıf [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) dosyaları indirmek için zaman uyumsuz destek sağlar.  
  
 Zaman uyumsuz adlar ile COM uygulamanızı Internet üzerinden zaman uyumsuz olarak indirmek ve bit eşlemler gibi büyük nesneler ve VRML nesnelerin aşamalı işleme sağlamak için genişletebilirsiniz. Zaman uyumsuz adlar ActiveX denetimi özelliğini ya da kullanıcı arabiriminin yanıt engellenmeden yüklenmek üzere Internet üzerindeki bir dosya etkinleştirin.  
  
## <a name="advantages-of-asynchronous-monikers"></a>Zaman uyumsuz adlar avantajları  
 Zaman uyumsuz adlar kullanabilirsiniz:  
  
-   Kod ve dosyaları engellenmeden indirin.  
  
-   ActiveX denetimleri özelliklerinde engellenmeden indirin.  
  
-   İlerleme indirilmesi alın.  
  
-   İlerleme durumu ve hazır durumda bilgileri izler.  
  
-   İlerleme durumu hakkında kullanıcıya durum bilgileri sağlar.  
  
-   Herhangi bir zamanda yüklemeyi iptal etmek verin.  
  
## <a name="mfc-classes-for-asynchronous-monikers"></a>MFC sınıfları için zaman uyumsuz adlar  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) türetildiği [CMonikerFile](../mfc/reference/cmonikerfile-class.md), sırayla türetilen [COleStreamFile](../mfc/reference/colestreamfile-class.md). A `COleStreamFile` veri akışı a; bir nesneyi temsil eder `CMonikerFile` nesne kullanan bir `IMoniker` verileri elde etmek için ve bir `CAsyncMonikerFile` nesne mu bunu zaman uyumsuz olarak.  
  
 Zaman uyumsuz adlar, öncelikle Internet özellikli uygulamalar ve ActiveX denetimleri, dosya aktarımı sırasında bir yanıt kullanıcı arabirimi sağlamak için kullanılır. Bu prime örneği kullanımıdır [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) ActiveX denetimleri için zaman uyumsuz özellikler sağlamak için.  
  
## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>ActiveX denetimlerinde veri yolları için MFC sınıfları  
 MFC sınıfları `CDataPathProperty` ve [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) zaman uyumsuz olarak yüklenmesi gereken ActiveX denetimi özelliklerini uygulayın. Zaman uyumsuz özellikler sonra zaman uyumlu başlatma yüklenir. Zaman uyumsuz ActiveX denetimlerini art arda uzun özelliği exchange işlemi sırasında yeni verilerin kullanılabilirliğini belirtmek için bir geri çağırma.  
  
 `CDataPathProperty`türetilmiş `CAsyncMonikerFile`. `CCachedDataPathProperty`türetilmiş `CDataPathProperty`. ActiveX denetimlerinde zaman uyumsuz özellikler uygulamak için öğesinden bir sınıf türetin `CDataPathProperty` veya `CCachedDataPathProperty`ve geçersiz kılma [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) ve almak istediğiniz diğer bildirimleri.  
  
#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Zaman uyumsuz adlar kullanarak bir dosyayı indirmek için  
  
1.  Türetilmiş bir sınıf bildirme [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
2.  Geçersiz kılma [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) verileri görüntülemek için.  
  
3.  Dahil olmak üzere diğer üye işlevlerini geçersiz kılma [OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding), ve [OnStopBinding](../mfc/reference/casyncmonikerfile-class.md#onstopbinding).  
  
4.  Bu sınıfın örneğini bildirme ve URL'leri açmak için kullanın.  
  
 Zaman uyumsuz olarak bir ActiveX denetimini karşıdan yükleme hakkında daha fazla bilgi için bkz: [Internet'te ActiveX denetimleri](../mfc/activex-controls-on-the-internet.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama temelleri](../mfc/mfc-internet-programming-basics.md)

