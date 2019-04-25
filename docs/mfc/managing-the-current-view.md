---
title: Geçerli Görünümü Yönetme
ms.date: 11/04/2016
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
ms.openlocfilehash: a926a9e31f7c43ab625220a4d759f6d536c2a77f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173346"
---
# <a name="managing-the-current-view"></a>Geçerli Görünümü Yönetme

Çerçeve pencereleri varsayılan uygulaması bir parçası olarak, bir çerçeve penceresi şu anda etkin bir görünüm izler. Çerçeve penceresi bir ayırıcı penceresi örnekte olduğu gibi birden fazla görünümü içeriyorsa, geçerli görünüm kullanımda en son görünümdür. Etkin görünüm, Windows veya giriş odağını geçerli etkin pencereyi bağımsızdır.

Etkin görünüm değiştiğinde framework çağırarak geçerli görünümü bildirir, [OnActivateView](../mfc/reference/cview-class.md#onactivateview) üye işlevi. Görünüm olup olmadığını söyleyebilir etkin veya devre dışı inceleyerek `OnActivateView`'s *bActivate* parametresi. Varsayılan olarak, `OnActivateView` etkinleştirme geçerli görünüm için odak noktası ayarlar. Geçersiz kılabilirsiniz `OnActivateView` görünümü devre dışı veya yeniden etkinleştiren, özel bir işlem gerçekleştirmek için. Örneğin, etkin görünüm, etkin olmayan diğer görünümleri ayırt etmek için özel görsel ipuçlarını sağlama isteyebilirsiniz.

Bölümünde anlatıldığı gibi bir çerçeve penceresi komutları, geçerli (etkin) görünümüne iletir [komut yönlendirme](../mfc/command-routing.md), standart komut yönlendirmeyi bir parçası olarak.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)
