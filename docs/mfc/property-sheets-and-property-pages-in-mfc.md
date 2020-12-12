---
description: "Daha fazla bilgi edinin: MFC 'de Özellik sayfaları ve özellik sayfaları"
title: MFC'de Özellik Bölümleri ve Özellik Sayfaları
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: 93662dcf07e2810ad9f4f51d6df8341f9f6df6dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185433"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC'de Özellik Bölümleri ve Özellik Sayfaları

Sekme iletişim kutusu olarak da bilinen bir özellik sayfası, özellik sayfaları içeren bir iletişim kutusudur. Her özellik sayfası bir iletişim kutusu şablonu kaynağını temel alır ve denetimleri içerir. En üstteki bir sekmeye sahip bir sayfada bulunur. Sekme, sayfayı adlandırır ve amacını gösterir. Kullanıcılar bir denetim kümesi seçmek için özellik sayfasındaki bir sekmeye tıkla,.

Özellik sayfasındaki denetimleri anlamlı kümeler halinde gruplandırmak için sayfaları kullanın. Kapsanan Özellik sayfası genellikle kendi kendine birkaç denetime sahiptir. Bunlar tüm sayfalar için geçerlidir.

Özellik sayfaları, [CPropertySheet](../mfc/reference/cpropertysheet-class.md)sınıfına dayalıdır. Özellik sayfaları, [CPropertyPage](../mfc/reference/cpropertypage-class.md)sınıfına dayalıdır.

Bir özellik sayfası, bir görünümdeki geçerli seçim gibi bazı dış nesnelerin özniteliklerini değiştirmek için genellikle kullanılan özel bir tür iletişim kutusudur. Özellik sayfasında üç ana bölüm bulunur: kapsayan iletişim kutusu, tek seferde görüntülenen bir veya daha fazla özellik sayfası ve kullanıcının bu sayfayı seçmek için tıklattığı her sayfanın üst kısmında bir sekme. Özellik sayfaları, değişen birkaç ayar veya seçenek grubunun olduğu durumlarda faydalıdır. Özellik sayfası, bilgileri kolayca anlamış bir şekilde gruplandırır.

> [!NOTE]
> Kullanarak bir özellik sayfası göstermeye çalışırken `CPropertySheet::DoModal` sistem bir ilk şans özel durumu oluşturabilir. Bu özel durum, sistem, nesne oluşturulmadan önce nesnenin [pencere stillerini](../mfc/reference/styles-used-by-mfc.md#window-styles) değiştirmeye çalıştığı için oluşur. Bu özel durum hakkında daha fazla bilgi ve ayrıca bunu önlemek veya işlemek için bkz. [CPropertySheet::D oModal](../mfc/reference/cpropertysheet-class.md#domodal).

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)
