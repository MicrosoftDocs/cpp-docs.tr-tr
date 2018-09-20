---
title: Özellik bölümleri ve özellik sayfaları MFC'de | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f35282ce46aff3a3f0fba5fca505653cd892a392
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430056"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC'de Özellik Bölümleri ve Özellik Sayfaları

Bir özellik sayfası olarak da bilinen bir sekme iletişim kutusu, özellik sayfaları içeren bir iletişim kutusudur. Her bir özellik sayfası iletişim şablon kaynağında temel alır ve denetimler de içerir. Bu sayfada en üstte bir sekme ile içine alınır. Sekme adları sayfası ve amacını gösterir. Kullanıcılar bir özellik sayfası bir dizi denetimi seçmek için sekmesinde'ı tıklatın.

Özellik sayfası denetimlerinde anlamlı kümeleri halinde gruplandırmak için sayfalarını kullanın. Kapsanan özellik sayfası, genellikle kendi çeşitli denetimler içerir. Bu, tüm sayfalara uygulanır.

Özellik sayfaları, sınıfta dayalı [CPropertySheet](../mfc/reference/cpropertysheet-class.md). Özellik sayfaları, sınıfta dayalı [CPropertyPage](../mfc/reference/cpropertypage-class.md).

Bir özellik sayfası iletişim kutusu, genel bir görünüm geçerli seçimde gibi bazı dış nesne özniteliklerini değiştirmek için kullanılan özel türüdür. Özellik sayfası üç ana bölümden oluşur: gösterilen birer birer ve bu sayfayı seçmek için kullanıcı tıkladığında her sayfanın üst kısmındaki sekme bir veya daha fazla özelliği içeren bir iletişim kutusu sayfaları. Özellik sayfaları ayarları ya da değiştirmek için seçenekler birkaç benzer grubuna sahip olduğu durumlar için kullanışlıdır. Bir özellik sayfası anlaşılması kolay bir şekilde bilgi gruplandırır.

> [!NOTE]
>  Bir özellik sayfasını kullanarak göstermek çalışırken `CPropertySheet::DoModal`, sistemin ilk fırsat özel durum oluşturabilir. Sistem değiştirilmeye çalışılırken özel durum oluşur [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles) nesne oluşturulmadan önce nesne. Bu özel durum ve onu önlemenin veya bunu işlemek nasıl hakkında daha fazla bilgi için bkz. [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal).

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)

