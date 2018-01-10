---
title: "MFC modüllerinin durum verisini yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d070bb91d9c1c229feaa563123c12702a7b5027
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC Modüllerinin Durum Verisini Yönetme
Bu makalede durumu verilerini MFC modülleri ve bu durum (yolu kod aracılığıyla bir uygulama yürütülürken alır) akışını girer ve bir modül çıktığında nasıl güncelleştirileceğini açıklar. Modül durumları ile geçiş `AFX_MANAGE_STATE` ve `METHOD_PROLOGUE` makroları da ele alınmıştır.  
  
> [!NOTE]
>  Terim "modülünde" Buraya yürütülebilir bir program veya bir DLL (veya kümesi DLL'ler), uygulamanın geri kalanına bağımsız olarak çalışan başvuruyor, ancak MFC DLL paylaşılan bir kopyasını kullanır. ActiveX denetimi, bir modül tipik örneğidir.  
  
 Aşağıdaki çizimde gösterildiği gibi MFC durumu verilerini bir uygulamada kullanılan her modül için vardır. Bu veri örneklerindendir Windows örneği tanıtıcıları (kaynakları yüklemek için kullanılan), geçerli işaretçiler `CWinApp` ve `CWinThread` bir uygulama, OLE modül başvurusu sayılarını ve arasındaki bağlantıları korumak eşlemeleri çeşitli nesneleri Windows tanıtıcı ve karşılık gelen örneklerini MFC nesneleri nesne. Bir uygulama birden fazla modülü kullandığında, Bununla birlikte, her modül durumu verileri uygulama değil geniş. Bunun yerine, her modül MFC'nin durumu verilerini kendi özel kopyasını sahiptir.  
  
 ![Durum verileri tek bir modül &#40; uygulama &#41; ] (../mfc/media/vc387n1.gif "vc387n1")  
Durum verileri tek bir modülün (uygulama)  
  
 Bir modülün durumu verilerini bir yapısında bulunan ve bu yapısına yönelik işaretçinin aracılığıyla her zaman kullanılabilir. Akış yürütme aşağıdaki resimde gösterildiği gibi belirli bir modülün girdiğinde, bu modülün durumu "geçerli" veya "etkin" durumunda olması gerekir. Bu nedenle, her iş parçacığı nesnesi uygulamasının etkin durumu yapısına yönelik işaretçinin sahiptir. Bu işaretçinin en güncel tutma katıdır uygulamanın genel durumunu yönetme ve her modülün durumu bütünlüğünü korumak için önemli. Genel durum, yanlış yönetim edilmesi öngörülemeyen uygulama davranışlarına yol açabilir.  
  
 ![Durum verileri birden çok modüllerin](../mfc/media/vc387n2.gif "vc387n2")  
Birden çok modüllerinin durum verisini  
  
 Diğer bir deyişle, her modül, modül durumları tüm giriş noktaları arasında doğru bir şekilde geçiş sorumludur. "Giriş noktası" yürütme akışı modülünün kod girebilecekleri bir yerdir. Giriş noktaları şunları içerir:  
  
-   [DLL'den dışarı aktarılan işlevler](../mfc/exported-dll-function-entry-points.md)  
  
-   [COM arabirimleri üye işlevleri](../mfc/com-interface-entry-points.md)  
  
-   [Pencere yordamları](../mfc/window-procedure-entry-points.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC Konuları](../mfc/general-mfc-topics.md)

