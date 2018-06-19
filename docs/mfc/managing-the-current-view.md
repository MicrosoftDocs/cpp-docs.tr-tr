---
title: Geçerli görünümü yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 323903d2e1285a4ee697bbd9d0c3a29c2e1248d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349597"
---
# <a name="managing-the-current-view"></a>Geçerli Görünümü Yönetme
Çerçeve pencereleri varsayılan uygulaması bir parçası olarak, bir çerçeve penceresinde şu anda etkin bir görünüm izler. Çerçeve penceresi Bölümlendirici pencere örnekte olduğu gibi birden çok görünüm içeriyorsa geçerli görünümü kullanımda en son görünümüdür. Etkin görünüm, etkin pencereyi Windows ya da geçerli giriş odağını bağımsızdır.  
  
 Etkin görünüm değiştiğinde çağırarak geçerli görünümü framework bildirir, [OnActivateView](../mfc/reference/cview-class.md#onactivateview) üye işlevi. Görünüm yüklenmekte olan olup olmadığını söyleyebilir etkin veya devre dışı inceleyerek `OnActivateView`'s `bActivate` parametresi. Varsayılan olarak, `OnActivateView` odağı etkinleştirme geçerli görünümde ayarlar. Geçersiz kılabilirsiniz `OnActivateView` görünümü devre dışı ya da yeniden hiçbir özel işlem gerçekleştirmek için. Örneğin, etkin görünümü diğer, etkin olmayan görünümleri ayırt etmek için özel görsel Yardım sağlamak isteyebilirsiniz.  
  
 Bölümünde açıklandığı gibi komutları, geçerli (etkin) görüntülemek için bir çerçeve penceresinde iletir [komut yönlendirme](../mfc/command-routing.md), standart komut yönlendirmeyi bir parçası olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

