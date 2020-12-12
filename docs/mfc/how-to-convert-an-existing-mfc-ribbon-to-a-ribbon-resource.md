---
description: 'Şu konuda daha fazla bilgi edinin: nasıl yapılır: varolan bir MFC şeridini şerit kaynağına dönüştürme'
title: 'Nasıl yapılır: Varolan Bir MFC Şeridini Şerit Kaynağına Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: 825b8b4e3322afd8919ffad0f5e0f73c9d52be78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290290"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Nasıl yapılır: Varolan Bir MFC Şeridini Şerit Kaynağına Dönüştürme

Şerit kaynakları, el ile kodlanmış şeritlere göre görselleştirme, değiştirme ve koruma işlemlerini kolaylaştırır. Bu konu başlığı altında, bir MFC projesindeki el ile kodlanmış bir şerit 'in bir şerit kaynağına nasıl dönüştürüleceği açıklanır.

MFC şerit sınıflarını kullanan kodu olan, örneğin [CMFCRibbonBar sınıfı](reference/cmfcribbonbar-class.md)olan bir MFC projenizin olması gerekir.

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Bir MFC şeridini şerit kaynağına dönüştürmek için

1. Visual Studio 'da, varolan bir MFC projesinde, nesnenin başlatıldığı kaynak dosyayı açın `CMFCRibbonBar` . Genellikle, dosya MainFrm. cpp ' dir. Şerit için başlatma kodundan sonra aşağıdaki kodu ekleyin.

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   Dosyayı kaydedin ve kapatın.

1. MFC uygulamasını derleyin ve çalıştırın, sonra Not defteri 'nde RibbonOutput.txt açın ve içeriğini kopyalayın.

1. Visual Studio 'da, **Proje** menüsünde **Kaynak Ekle**' ye tıklayın. **Kaynak Ekle** iletişim kutusunda, **Şerit** ' i seçin ve ardından **Yeni**' ye tıklayın.

   Visual Studio bir şerit kaynağı oluşturur ve Tasarım görünümünde açar. Şerit kaynak KIMLIĞI IDR_RIBBON1 **kaynak görünümü** görüntülenir. Şerit, Ribbon1. mfcribbon-ms XML dosyasında tanımlanmıştır.

1. Visual Studio 'da, Ribbon1. mfcribbon-ms ' i açın, içeriğini silin ve ardından daha önce kopyaladığınız RibbonOutput.txt içeriğini yapıştırın. Ribbon1. mfcribbon-ms ' i kaydedin ve kapatın.

1. Ardından, CMFCRibbonBar nesnesinin başlatıldığı kaynak dosyayı açın (genellikle, MainFrm. cpp) ve varolan Şerit kodunu açıklama olarak ekleyin. Yorum yaptığınız koddan sonra aşağıdaki kodu ekleyin.

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. Projeyi derleyin ve programı çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[Şerit Tasarımcısı (MFC)](ribbon-designer-mfc.md)
