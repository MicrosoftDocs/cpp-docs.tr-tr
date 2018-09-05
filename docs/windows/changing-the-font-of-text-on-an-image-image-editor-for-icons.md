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
ms.openlocfilehash: 0898d8a787c6d2c14f341a31e202738d666cdf86
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678470"
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>Görüntüdeki Metnin Yazı Tipini Değiştirme (Simgeler İçin Görüntü Düzenleyicisi)

Aşağıdaki yordam nasıl bir örneğidir:

- Bir Windows uygulamasındaki bir simge metin ekleme

- Yazı tipi, metin düzenleme

### <a name="to-change-the-font-of-text-on-an-image"></a>Görüntüdeki metnin yazı tipini değiştirmek için

1. Bir C++ Windows Forms uygulaması oluşturun. Ayrıntılar için bkz [bir Windows uygulaması projesi oluşturma](/previous-versions/visualstudio/visual-studio-2010/42wc9kk5\(v=vs.100\)). Bir `app.ico` dosya varsayılan olarak projenize eklenir.

2. İçinde **Çözüm Gezgini**, dosya n app.ico çift tıklayın. [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) açılır.

3. Gelen **görüntü** menüsünde **Araçları** seçip **metin aracı**. [Metin aracı iletişim kutusu](../windows/text-tool-dialog-box-image-editor-for-icons.md) görünür.

4. İçinde **metin aracı** iletişim kutusuna `C++` boş metin alanında. Bu metin kutusunda sol üst köşedeki bir yeniden boyutlandırılabilir görünür `app.ico`, **Resim Düzenleyicisi**.

5. İçinde **Resim Düzenleyicisi**, yeniden boyutlandırılabilir kutusunda metnin okunabilirliğini geliştirmek için n app.ico ortasına sürükleyin.

6. İçinde **metin aracı** iletişim kutusu, tıklayın **yazı tipi** düğmesi. [Metin aracı yazı tipi iletişim kutusu](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) görünür.

7. İçinde **metin aracı yazı tipi** iletişim kutusunda **Times yeni Roman** listelenen tiplerinin listesinden **yazı tipi** liste kutusu.

8. Seçin **kalın** listelenen kullanılabilir yazı tipi stillerini listesinden **yazı tipi stili** liste kutusu.

9. Seçin **10** listesinden kullanılabilir boyutları listelenen noktası **boyutu** liste kutusu.

10. Tıklayın **Tamam** düğmesi. **Metin aracı yazı tipi** iletişim kutusunu kapatmak ve yeni yazı tipi ayarlarını metninize uygulanır.

11. Tıklayın **Kapat** düğmesini **metin aracı** iletişim kutusu. Yeniden boyutlandırılabilir kutu çevresinde, metin alanından kaybolur **Resim Düzenleyicisi**.

## <a name="see-also"></a>Ayrıca Bkz.

[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Araç Çubuğu](../windows/toolbar-image-editor-for-icons.md)