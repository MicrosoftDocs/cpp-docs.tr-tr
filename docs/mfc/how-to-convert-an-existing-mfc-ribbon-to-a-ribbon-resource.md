---
title: 'Nasıl yapılır: Varolan Bir MFC Şeridini Şerit Kaynağına Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: 627c50758b10ad18e45fc1432340c0eb2dad7b19
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524371"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Nasıl yapılır: Varolan Bir MFC Şeridini Şerit Kaynağına Dönüştürme

Şerit kaynaklarını görselleştirin, değiştirebilir ve bakımını el ile kodlanmış bir Şerit kolaydır. Bu konu, el ile kodlanmış bir Şerit MFC projesinde bir Şerit kaynağına dönüştürme açıklar.

Örneğin, MFC Şerit sınıflarını kullanan kod sahip varolan bir MFC projesinde olmalıdır [CMFCRibbonBar sınıfı](../mfc/reference/cmfcribbonbar-class.md).

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Bir MFC şeridini Şerit kaynağına dönüştürmek için

1. Visual Studio'da var olan bir MFC projesinde kaynak dosyasını açın. burada `CMFCRibbonBar` nesnesi. Genellikle, mainfrm.cpp dosyasıdır. Şerit başlatma kodunu sonra aşağıdaki kodu ekleyin.

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   Dosyayı kaydedin ve kapatın.

1. Derleme ve MFC uygulamasını çalıştırın ve ardından RibbonOutput.txt Not Defteri'nde açın ve içeriğini kopyalayın.

1. Visual Studio'da üzerinde **proje** menüsünü tıklatın **kaynak Ekle**. İçinde **kaynak Ekle** iletişim kutusunda **Şerit** ve ardından **yeni**.

   Visual Studio, bir Şerit kaynağı oluşturur ve Tasarım Görünümü'nde açılır. Görüntülenen IDR_RIBBON1, Şerit kaynak kimliğidir **kaynak görünümü**. Şerit ribbon1.mfcribbon ms XML dosyasında tanımlanır.

1. Visual Studio'da ribbon1.mfcribbon ms açın, içeriğini silin ve ardından daha önce kopyaladığınız RibbonOutput.txt içeriğini yapıştırın. Kaydedip ribbon1.mfcribbon ms kapatın.

1. CMFCRibbonBar nesne nerede başlatılır kaynak dosyasını tekrar açın (genellikle mainfrm.cpp) ve açıklama var olan çıkış kodu Şerit. Açıklama satırı koddan sonra aşağıdaki kodu ekleyin.

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. Projeyi oluşturmak ve programı çalıştırın.

## <a name="see-also"></a>Ayrıca Bkz.

[Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

