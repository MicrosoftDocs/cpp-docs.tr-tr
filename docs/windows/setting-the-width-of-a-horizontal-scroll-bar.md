---
title: Yatay Kaydırma Çubuğunun Genişliğini Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
ms.openlocfilehash: 393571b79d27485e840d150549208c899e8ed1d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625959"
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>Yatay Kaydırma Çubuğunun Genişliğini Ayarlama

MFC sınıfları kullanarak iletişim kutusuna bir yatay kaydırma çubuğu içeren bir liste kutusu eklediğinizde, kaydırma çubuğu uygulamanızı otomatik olarak görünmez.

### <a name="to-make-the-scroll-bar-appear"></a>Kaydırma çubuğunun görünmesi için

1. Çağırarak geniş öğesi için bir maksimum genişliğini ayarlamak [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) kodunuzda.

   Bu değer kümesi kaydırma çubuğu görünmez, hatta öğeleri liste kutusunda kutudan daha geniş olduğunda.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)