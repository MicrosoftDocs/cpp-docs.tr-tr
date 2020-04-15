---
title: İleti Eşlemelerinin Bulunduğu Yer
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: eec0ae43546e3cc0c08e3178c4808e21fa48686a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360159"
---
# <a name="where-to-find-message-maps"></a>İleti Eşlemelerinin Bulunduğu Yer

Uygulama Sihirbazı ile yeni bir iskelet uygulaması oluşturduğunuzda, Uygulama Sihirbazı sizin için oluşturduğu her komut hedefi sınıfı için bir ileti eşlemi yazar. Bu, türetilmiş uygulamanızı, belgenizi, görünümünüzü ve çerçeve pencere sınıflarınızı içerir. Bu ileti eşlemlerinden bazıları zaten belirli iletiler ve önceden tanımlanmış komutlar için Uygulama Sihirbazı tarafından sağlanan girişlere sahiptir ve bazıları yalnızca ekleyeceğiniz işleyiciler için yer tutuculardır.

Sınıfın ileti eşlemi. Sınıf için CPP dosyası. Uygulama Sihirbazı'nın oluşturduğu temel ileti eşlemleriyle çalışırken, her sınıfın işleyeceğinin iletiler ve komutlar için girişler eklemek için [Sınıf Sihirbazı'nı](reference/mfc-class-wizard.md) kullanırsınız. Bazı girişler ekledikten sonra tipik bir ileti eşlemi aşağıdaki gibi görünebilir:

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

İleti eşlemi makrolar koleksiyonundan oluşur. [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) ve [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)olmak üzere iki makro, ileti eşlemi dir. İleti eşleminin `ON_COMMAND`içeriğini doldurmak gibi diğer makrolar.

> [!NOTE]
> İleti-eşlemi makroları yarım kolon tarafından takip edilmez.

Yeni bir sınıf oluşturmak için Sınıf Ekle sihirbazını kullandığınızda, sınıf için bir ileti eşlemi sağlar. Alternatif olarak, kaynak kodu düzenleyicisini kullanarak el ile bir ileti eşlemi oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Mesaj Eşlemlerini Nasıl Arar?](../mfc/how-the-framework-searches-message-maps.md)
