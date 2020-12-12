---
description: 'Hakkında daha fazla bilgi edinin: Ileti haritaları nerede bulunur'
title: İleti Eşlemelerinin Bulunduğu Yer
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: 4796d358dd3be5455b22e348fbcc9236d1404ce8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284973"
---
# <a name="where-to-find-message-maps"></a>İleti Eşlemelerinin Bulunduğu Yer

Uygulama Sihirbazı ile yeni bir iskelet uygulaması oluşturduğunuzda, uygulama Sihirbazı sizin için oluşturduğu her bir komut hedef sınıfı için bir ileti haritası yazar. Bu türetilmiş uygulamanızı, belgenizi, görünümü ve çerçeve pencere sınıflarını içerir. Bu ileti eşlemlerinden bazıları, bazı iletiler ve önceden tanımlanmış komutlar için uygulama Sihirbazı tarafından sağlanan girişlere zaten sahiptir ve bazıları yalnızca ekleyeceğiniz işleyiciler için yer tutuculardır.

Bir sınıfın ileti eşlemesi içinde bulunur. Sınıf için CPP dosyası. Uygulama Sihirbazı 'nın oluşturduğu temel ileti eşlemeleriyle birlikte çalışarak, her sınıfın işleyeceği ileti ve komutlara yönelik girdiler eklemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanırsınız. Tipik bir ileti eşlemesi, bazı girdiler eklendikten sonra aşağıdaki gibi görünebilir:

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

İleti eşlemesi bir makro koleksiyonundan oluşur. İki makro, [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) ve [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), ileti eşlemine parantez. Gibi diğer makrolar `ON_COMMAND` ileti haritasının içeriğini de doldurur.

> [!NOTE]
> İleti eşleme makrolarının sonunda noktalı virgül yoktur.

Yeni bir sınıf oluşturmak için sınıf ekleme Sihirbazı ' nı kullandığınızda, sınıfı için bir ileti haritası sağlar. Alternatif olarak, kaynak kodu düzenleyicisini kullanarak el ile bir ileti haritası da oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Ileti eşlemelerini nasıl arar](../mfc/how-the-framework-searches-message-maps.md)
