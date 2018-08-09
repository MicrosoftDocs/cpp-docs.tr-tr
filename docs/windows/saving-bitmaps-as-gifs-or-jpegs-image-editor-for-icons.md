---
title: Bit eşlemleri GIF veya JPEG (simgeler için görüntü Düzenleyicisi) olarak kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- .gif files, saving bitmaps as
- jpg files, saving bitmaps as
- jpeg files, saving bitmaps as
- .jpg files, saving bitmaps as
- Image editor [C++], converting image formats
- gif files, saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files, saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: debb2b1e8435cc53ec82ab1f957710850d7b5de3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010697"
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>Bit Eşlemleri GIF veya JPEG Olarak Kaydetme (Simgeler İçin Görüntü Düzenleyicisi)
Bir bit eşlem oluşturduğunuzda, görüntü bit eşlem (.bmp) biçiminde oluşturulur. Ancak, görüntünün bir GIF veya JPEG olarak veya diğer grafik biçimlerde tasarruf edebilirsiniz.  
  
> [!NOTE]
>  Bu işlem, simgeler ve İmleçler için geçerli değildir.  
  
### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Oluşturmak ve bir bit eşlem .gif veya .jpeg olarak kaydetmek için  
  
1.  Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.  
  
2.  İçinde **yeni dosya iletişim kutusu**, tıklayın **Visual C++** klasörünü seçip **bit eşlem dosyası (.bmp)** içinde **şablonları** kutusuna ve tıklatın **Açık**.  
  
     Bit eşlem açılır **görüntü** Düzenleyici.  
  
3.  Yeni, bit eşlem için gerekli değişiklikleri yapın.  
  
4.  Bit eşlem içinde açık olan **görüntü** Düzenleyicisi, **Kaydet *filename*.bmp olarak** üzerinde **dosya** menüsü.  
  
5.  İçinde **dosyayı farklı Kaydet** iletişim kutusuna, dosya ve istediğiniz dosya biçimini gösterir uzantısı vermek istediğiniz adı yazın **dosya adı** kutusu. Örneğin, *myfile.gif*.  
  
     > [!NOTE]
     > Oluşturma veya başka bir dosya biçiminde kaydetmek için projenizin dışında bit eşlem açmak gerekir. Oluşturur veya kendi projesi içinde açın **Kaydet** komutu kullanılamaz. Daha fazla bilgi için [kaynaklar içinde bir kaynak betik dosyası dışında sonuna bir proje (tek başına) görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
6.  **Kaydet**'e tıklayın.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)