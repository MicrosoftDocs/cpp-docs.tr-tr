---
title: (Simgeler için görüntü Düzenleyicisi) görüntüdeki metnin yazı tipini değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 16d01d634b44b4e6da425c40e011106021638305
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461744"
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>Görüntüdeki Metnin Yazı Tipini Değiştirme (Simgeler İçin Görüntü Düzenleyicisi)
Aşağıdaki yordam nasıl bir örneğidir:  
  
-   Bir Windows uygulamasındaki bir simge metin ekleme  
  
-   Yazı tipi, metin düzenleme  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>Görüntüdeki metnin yazı tipini değiştirmek için  
  
1.  Bir C++ Windows Forms uygulaması oluşturun. Ayrıntılar için bkz [bir Windows uygulaması projesi oluşturma](http://msdn.microsoft.com/b2f93fed-c635-4705-8d0e-cf079a264efa). [Windows Forms uygulaması şablonu](http://msdn.microsoft.com/1babdebf-ab3f-4a64-a608-98499a5b9cea) n app.ico projeniz için varsayılan olarak adlandırılan bir dosya ekler.  
  
2.  Çözüm Gezgini'nde dosya n app.ico çift tıklayın. [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) açılır.  
  
3.  Gelen **görüntü** menüsünde **Araçları** seçip **metin aracı**. [Metin aracı iletişim kutusu](../windows/text-tool-dialog-box-image-editor-for-icons.md) görünür.  
  
4.  İçinde **metin aracı** iletişim kutusuna `C++` boş metin alanında. Bu metin, n app.ico, sol üst köşesinde bulunan yeniden boyutlandırılabilir kutusunda görünür **Resim Düzenleyicisi**.  
  
5.  İçinde **Resim Düzenleyicisi**, yeniden boyutlandırılabilir kutusunda metnin okunabilirliğini geliştirmek için n app.ico ortasına sürükleyin.  
  
6.  İçinde **metin aracı** iletişim kutusu, tıklayın **yazı tipi** düğmesi. [Metin aracı yazı tipi iletişim kutusu](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) görünür.  
  
7.  İçinde **metin aracı yazı tipi** iletişim kutusunda **Times yeni Roman** listelenen tiplerinin listesinden **yazı tipi** liste kutusu.  
  
8.  Seçin **kalın** listelenen kullanılabilir yazı tipi stillerini listesinden **yazı tipi stili** liste kutusu.  
  
9. Seçin **10** listesinden kullanılabilir boyutları listelenen noktası **boyutu** liste kutusu.  
  
10. Tıklayın **Tamam** düğmesi. **Metin aracı yazı tipi** iletişim kutusunu kapatmak ve yeni yazı tipi ayarlarını metninize uygulanır.  
  
11. Tıklayın **Kapat** düğmesini **metin aracı** iletişim kutusu. Yeniden boyutlandırılabilir kutu çevresinde, metin, Resim Düzenleyicisi'nden kaybolur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Araç Çubuğu](../windows/toolbar-image-editor-for-icons.md)