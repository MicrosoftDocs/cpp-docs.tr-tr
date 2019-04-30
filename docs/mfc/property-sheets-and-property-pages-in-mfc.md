---
title: MFC'de Özellik Bölümleri ve Özellik Sayfaları
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: fa8ee3518ad2b32e0eace77f0961eb86ccde1822
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391380"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC'de Özellik Bölümleri ve Özellik Sayfaları

Bir özellik sayfası olarak da bilinen bir sekme iletişim kutusu, özellik sayfaları içeren bir iletişim kutusudur. Her bir özellik sayfası iletişim şablon kaynağında temel alır ve denetimler de içerir. Bu sayfada en üstte bir sekme ile içine alınır. Sekme adları sayfası ve amacını gösterir. Kullanıcılar bir özellik sayfası bir dizi denetimi seçmek için sekmesinde'ı tıklatın.

Özellik sayfası denetimlerinde anlamlı kümeleri halinde gruplandırmak için sayfalarını kullanın. Kapsanan özellik sayfası, genellikle kendi çeşitli denetimler içerir. Bu, tüm sayfalara uygulanır.

Özellik sayfaları, sınıfta dayalı [CPropertySheet](../mfc/reference/cpropertysheet-class.md). Özellik sayfaları, sınıfta dayalı [CPropertyPage](../mfc/reference/cpropertypage-class.md).

Bir özellik sayfası iletişim kutusu, genel bir görünüm geçerli seçimde gibi bazı dış nesne özniteliklerini değiştirmek için kullanılan özel türüdür. Özellik sayfası üç ana bölümden oluşur: gösterilen birer birer ve bu sayfayı seçmek için kullanıcı tıkladığında her sayfanın üst kısmındaki sekme bir veya daha fazla özelliği içeren bir iletişim kutusu sayfaları. Özellik sayfaları ayarları ya da değiştirmek için seçenekler birkaç benzer grubuna sahip olduğu durumlar için kullanışlıdır. Bir özellik sayfası anlaşılması kolay bir şekilde bilgi gruplandırır.

> [!NOTE]
>  Bir özellik sayfasını kullanarak göstermek çalışırken `CPropertySheet::DoModal`, sistemin ilk fırsat özel durum oluşturabilir. Sistem değiştirilmeye çalışılırken özel durum oluşur [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles) nesne oluşturulmadan önce nesne. Bu özel durum ve onu önlemenin veya bunu işlemek nasıl hakkında daha fazla bilgi için bkz. [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal).

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)
