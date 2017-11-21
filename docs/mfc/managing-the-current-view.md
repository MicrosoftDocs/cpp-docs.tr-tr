---
title: "Geçerli görünümü yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 339a3677783b789c6026dc0e46c09cfdb1d2e451
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="managing-the-current-view"></a>Geçerli Görünümü Yönetme
Çerçeve pencereleri varsayılan uygulaması bir parçası olarak, bir çerçeve penceresinde şu anda etkin bir görünüm izler. Çerçeve penceresi Bölümlendirici pencere örnekte olduğu gibi birden çok görünüm içeriyorsa geçerli görünümü kullanımda en son görünümüdür. Etkin görünüm, etkin pencereyi Windows ya da geçerli giriş odağını bağımsızdır.  
  
 Etkin görünüm değiştiğinde çağırarak geçerli görünümü framework bildirir, [OnActivateView](../mfc/reference/cview-class.md#onactivateview) üye işlevi. Görünüm yüklenmekte olan olup olmadığını söyleyebilir etkin veya devre dışı inceleyerek `OnActivateView`'s `bActivate` parametresi. Varsayılan olarak, `OnActivateView` odağı etkinleştirme geçerli görünümde ayarlar. Geçersiz kılabilirsiniz `OnActivateView` görünümü devre dışı ya da yeniden hiçbir özel işlem gerçekleştirmek için. Örneğin, etkin görünümü diğer, etkin olmayan görünümleri ayırt etmek için özel görsel Yardım sağlamak isteyebilirsiniz.  
  
 Bölümünde açıklandığı gibi komutları, geçerli (etkin) görüntülemek için bir çerçeve penceresinde iletir [komut yönlendirme](../mfc/command-routing.md), standart komut yönlendirmeyi bir parçası olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)

