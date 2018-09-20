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
- .gif files [C++], saving bitmaps as
- jpg files [C++], saving bitmaps as
- jpeg files [C++], saving bitmaps as
- .jpg files [C++], saving bitmaps as
- Image editor [C++], converting image formats
- gif files [C++], saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files [C++], saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11eea641132a608bf780f9adcc7cfeafad0950d5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383147"
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>Bit Eşlemleri GIF veya JPEG Olarak Kaydetme (Simgeler İçin Görüntü Düzenleyicisi)

Bir bit eşlem oluşturduğunuzda, görüntü bit eşlem (.bmp) biçiminde oluşturulur. Ancak, görüntünün bir GIF veya JPEG olarak veya diğer grafik biçimlerde tasarruf edebilirsiniz.

> [!NOTE]
> Bu işlem, simgeler ve İmleçler için geçerli değildir.

### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Oluşturmak ve bir bit eşlem .gif veya .jpeg olarak kaydetmek için

1. Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.

2. İçinde **yeni dosya iletişim kutusu**, tıklayın **Visual C++** klasörünü seçip **bit eşlem dosyası (.bmp)** içinde **şablonları** kutusuna ve tıklatın **Açık**.

   Bit eşlem açılır **görüntü** Düzenleyici.

3. Yeni, bit eşlem için gerekli değişiklikleri yapın.

4. Bit eşlem içinde açık olan **görüntü** Düzenleyicisi, **Kaydet *filename*.bmp olarak** üzerinde **dosya** menüsü.

5. İçinde **dosyayı farklı Kaydet** iletişim kutusuna, dosya ve istediğiniz dosya biçimini gösterir uzantısı vermek istediğiniz adı yazın **dosya adı** kutusu. Örneğin, *myfile.gif*.

   > [!NOTE]
   > Oluşturma veya başka bir dosya biçiminde kaydetmek için projenizin dışında bit eşlem açmak gerekir. Oluşturur veya kendi projesi içinde açın **Kaydet** komutu kullanılamaz. Daha fazla bilgi için [kaynaklar içinde bir kaynak betik dosyası dışında sonuna bir proje (tek başına) görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

6. **Kaydet**'e tıklayın.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="see-also"></a>Ayrıca Bkz.

[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)