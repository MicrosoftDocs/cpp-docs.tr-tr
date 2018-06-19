---
title: Görüntüdeki (simgeler için görüntü Düzenleyicisi) metnin yazı tipini değiştirme | Microsoft Docs
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
ms.openlocfilehash: b3ddef7e52866d5e25c3b9f5e5c580062f73e1b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860898"
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
 [Araç Çubuğu](../windows/toolbar-image-editor-for-icons.md)

