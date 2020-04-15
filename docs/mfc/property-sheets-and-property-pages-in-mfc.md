---
title: MFC'de Özellik Bölümleri ve Özellik Sayfaları
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: 10fb34c79745e672d30dd2d3c3b97d457583f795
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371180"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC'de Özellik Bölümleri ve Özellik Sayfaları

Sekme iletişim kutusu olarak da bilinen özellik sayfası, özellik sayfaları içeren bir iletişim kutusudur. Her özellik sayfası bir iletişim şablonu kaynağını temel alıyor ve denetimler içeriyor. Üstte sekme olan bir sayfaya eklenir. Sekme sayfayı adlandırır ve amacını gösterir. Kullanıcılar bir denetim kümesi seçmek için özellik sayfasındaki bir sekmeyi tıklattı.

Özellik sayfasındaki denetimleri anlamlı kümelere gruplandırmak için sayfaları kullanın. İçerdiği özellik sayfası genellikle kendi başına birkaç denetime sahiptir. Bunlar tüm sayfalar için geçerlidir.

Özellik sayfaları sınıf [CPropertySheet](../mfc/reference/cpropertysheet-class.md)dayanmaktadır. Özellik sayfaları [cpropertypage](../mfc/reference/cpropertypage-class.md)sınıfı dayanmaktadır.

Özellik sayfası, görünümdeki geçerli seçim gibi bazı dış nesnelerin özniteliklerini değiştirmek için genellikle kullanılan özel bir iletişim kutusu türüdür. Özellik sayfasının üç ana bölümü vardır: içeren iletişim kutusu, birer birer gösterilen bir veya daha fazla özellik sayfası ve kullanıcının bu sayfayı seçmek için tıklatdığı her sayfanın üst kısmında ki bir sekme. Özellik sayfaları, değiştirmek için birkaç benzer ayar veya seçenek grubunuzun olduğu durumlar için yararlıdır. Bir özellik sayfası bilgileri kolayca anlaşılmış bir şekilde gruplar.

> [!NOTE]
> Bir özellik sayfasını kullanarak `CPropertySheet::DoModal`göstermeye çalıştığınızda, sistem ilk şans özel durumu oluşturabilir. Bu özel durum, sistem nesne oluşturulmadan önce nesnenin [Pencere Stillerini](../mfc/reference/styles-used-by-mfc.md#window-styles) değiştirmeye çalıştığından oluşur. Bu özel durum hakkında daha fazla bilgi için, ve aynı zamanda nasıl önlemek veya işlemek için, [CPropertySheet bakın::DoModal](../mfc/reference/cpropertysheet-class.md#domodal).

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../mfc/property-sheets-mfc.md)
