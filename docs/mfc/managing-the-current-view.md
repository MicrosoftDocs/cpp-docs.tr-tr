---
description: 'Hakkında daha fazla bilgi edinin: geçerli görünümü yönetme'
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
ms.openlocfilehash: 9c9acd315636ea33c52fbe63374b5afacef95247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283348"
---
# <a name="managing-the-current-view"></a>Geçerli Görünümü Yönetme

Çerçeve pencerelerinin varsayılan uygulamasının bir parçası olarak, bir çerçeve penceresi şu anda etkin olan görünümü izler. Çerçeve penceresi birden fazla görünüm içeriyorsa (örneğin, bir bölücü penceresinde), geçerli görünüm kullanımda olan en son görünümüdür. Etkin görünüm, Windows 'daki etkin pencereden veya geçerli giriş odağında bağımsızdır.

Etkin görünüm değiştiğinde Framework, [OnActivateView](reference/cview-class.md#onactivateview) üye işlevini çağırarak geçerli görünümü bilgilendirir. Arka uç parametresini inceleyerek görünümün etkinleştirilip etkinleştirilmediğini veya devre dışı bırakıldığını söyleyebilirsiniz `OnActivateView` .  Varsayılan olarak, `OnActivateView` etkinleştirme sırasında odağı geçerli görünüme ayarlar. `OnActivateView`Görünüm devre dışı bırakıldığında veya yeniden etkinleştirildiğinde özel bir işlem gerçekleştirmek için geçersiz kılabilirsiniz. Örneğin, etkin görünümü diğer, etkin olmayan görünümlerden ayırt etmek için özel görsel ipuçları sağlamak isteyebilirsiniz.

Bir çerçeve penceresi komutları, standart komut yönlendirmenin bir parçası olarak [komut yönlendirme](command-routing.md)bölümünde açıklandığı gibi geçerli (etkin) görünümüne iletir.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencerelerini kullanma](using-frame-windows.md)
