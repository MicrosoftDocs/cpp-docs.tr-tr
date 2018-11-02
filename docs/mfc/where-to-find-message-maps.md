---
title: İleti Eşlemelerinin Bulunduğu Yer
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: ab21369cecfa977a8397e7e2a7e68394e86e6927
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533477"
---
# <a name="where-to-find-message-maps"></a>İleti Eşlemelerinin Bulunduğu Yer

Uygulama sihirbazıyla yeni bir çatı uygulama oluşturduğunuzda, Uygulama Sihirbazı'nı sizin için oluşturduğu her komut hedefi sınıfı için ileti eşlemesi yazar. Bu, türetilmiş bir uygulama, belge, Görünüm ve çerçeve penceresi sınıfları içerir. Bu ileti eşlemeleri bazıları belirli iletileri ve önceden tanımlanmış komutları için Uygulama Sihirbazı tarafından sağlanan girişler zaten varsa ve ekleyeceğiniz işleyicileri yalnızca yer tutucular bazılarıdır.

Bir sınıfın ileti eşlemesi bulunur. Sınıf için CPP dosyasının. Uygulama Sihirbazı oluşturur temel ileti eşlemeleri ile çalışmak, Özellikler penceresinde iletileri ve her sınıf işleyecek komutları girdileri eklemek üzere kullanın. Bazı girişler ekledikten sonra tipik bir ileti eşlemesi aşağıdakine benzeyebilir:

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

İleti eşleme makroları koleksiyonunu oluşur. İki makro [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) ve [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), ileti eşlemesi köşeli ayraç. Diğer makrolar gibi `ON_COMMAND`, ileti haritanın içerikleri doldurun.

> [!NOTE]
>  İleti eşleme makroları, noktalı virgül tarafından izlenmeyen.

Yeni bir sınıf oluşturmak için Sınıf Ekle sihirbazını kullandığınızda, ileti eşlemesi için sınıf sağlar. Alternatif olarak, Kaynak Kod Düzenleyicisi'ni kullanarak el ile ileti eşlemesi oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İleti Eşlemelerini Araması](../mfc/how-the-framework-searches-message-maps.md)

