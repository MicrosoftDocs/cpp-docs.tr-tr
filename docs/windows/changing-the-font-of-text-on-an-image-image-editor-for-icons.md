---
title: "Görüntüdeki (simgeler için görüntü Düzenleyicisi) metnin yazı tipini değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07dc7d7fd74ad9d4b0229ffef7cf4e96a4ea44b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>Görüntüdeki Metnin Yazı Tipini Değiştirme (Simgeler İçin Görüntü Düzenleyicisi)
Aşağıdaki yordam, nasıl örneğidir:  
  
-   Simge bir Windows uygulamasında metin ekleyin  
  
-   Metnin yazı tipini değiştirmek  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>Görüntüdeki metnin yazı tipini değiştirmek için  
  
1.  C++ Windows Forms uygulaması oluşturma. Ayrıntılar için bkz [Windows uygulaması projesi oluşturma](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa). [Windows Forms uygulaması şablonu](http://msdn.microsoft.com/en-us/1babdebf-ab3f-4a64-a608-98499a5b9cea) n app.ico projenize varsayılan olarak adlandırılan bir dosyayı ekler.  
  
2.  Çözüm Gezgini'nde dosya n app.ico çift tıklayın. [Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md) açılır.  
  
3.  Gelen **görüntü** menüsünde, select **Araçları** ve ardından **metin aracı**. [Metin aracı iletişim kutusu](../windows/text-tool-dialog-box-image-editor-for-icons.md) görünür.  
  
4.  Metin aracı iletişim kutusuna yazın `C++` boş metin alanındaki. Bu metin, n app.ico, görüntü Düzenleyicisi'nde sol üst köşesinde bulunan yeniden boyutlandırılabilir kutusunda görüntülenir.  
  
5.  Görüntü Düzenleyicisi'nde, metnin okunabilirliğini artırmak için n app.ico, merkezine yeniden boyutlandırılabilir kutusunu sürükleyin.  
  
6.  Metin aracı iletişim kutusunda tıklatın **yazı tipi** düğmesi. [Metin aracı yazı tipi iletişim kutusu](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) görünür.  
  
7.  Metin aracı yazı tipi iletişim kutusu seç **kez yeni Latin** listelenen kullanılabilir yazı tipleri listesinden **yazı tipi** liste kutusu.  
  
8.  Seçin **kalın** listelenen kullanılabilir yazı tipi stillerini listesinden **yazı tipi stilini** liste kutusu.  
  
9. Seçin **10** listesinden kullanılabilir noktası listelenen boyutları **boyutu** liste kutusu.  
  
10. Tıklatın **Tamam** düğmesi. Metin aracı yazı tipi iletişim kutusu kapanır ve yeni yazı tipi ayarlarını metninizi için geçerli olacaktır.  
  
11. Tıklatın **Kapat** metin aracı iletişim kutusu düğmesinde. Görüntü Düzenleyicisi'nden metninizi çevresinde yeniden boyutlandırılabilir kutu kaybolur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Araç çubuğu](../windows/toolbar-image-editor-for-icons.md)

