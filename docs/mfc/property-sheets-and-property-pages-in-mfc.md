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
ms.openlocfilehash: a54469672c67e43d3692bc47d0b3efa00c18f8f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC'de Özellik Bölümleri ve Özellik Sayfaları
Özellik sayfasını, olarak da bilinen bir sekme iletişim kutusu, özellik sayfaları içeren bir iletişim kutusudur. Her özellik sayfası, bir iletişim şablon kaynağını temel ve denetimleri içerir. Bu sayfada üst sekmesinde ile içine alınır. Sekme adları sayfası ve amacını gösterir. Kullanıcı denetimleri kümesini seçmek için özellik sayfasında bir sekmesini tıklatın.  
  
 Özellik sayfasını denetimlerinde anlamlı kümeleri halinde gruplandırmak için sayfalarını kullanın. Kapsanan özellik sayfasında genellikle kendi birkaç denetimleri vardır. Bu, tüm sayfalar için geçerlidir.  
  
 Özellik sayfaları sınıfında dayalı [CPropertySheet](../mfc/reference/cpropertysheet-class.md). Özellik sayfaları sınıfında dayalı [CPropertyPage](../mfc/reference/cpropertypage-class.md).  
  
 Özellik sayfasını, genellikle bir görünüm geçerli seçim gibi bazı dış nesnenin özniteliklerini değiştirmek için kullanılan iletişim kutusunda özel türüdür. Özellik sayfasında üç ana bölümü vardır: gösterilen birer birer ve kullanıcı bu sayfayı seçmek için her sayfanın üstündeki sekme içeren iletişim kutusu, bir veya daha fazla özellik sayfaları. Özellik sayfaları ayarları ya da değiştirmek için seçenekleri birkaç benzer gruplar sahip olduğu durumlarda faydalıdır. Bir özellik sayfası kolay anlaşılır bir biçimde bilgileri gruplandırır.  
  
> [!NOTE]
>  Ne zaman çalıştığınız özellik sayfasını kullanarak Göster `CPropertySheet::DoModal`, sistem ilk fırsat özel durum oluşturabilir. Sistem değiştirmeye çalışıyor olduğundan bu özel durum oluştu [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles) nesne oluşturulmadan önce nesnenin. Bu özel durumu ve ayrıca engellemek ya da işlemek nasıl hakkında daha fazla bilgi için bkz: [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)

