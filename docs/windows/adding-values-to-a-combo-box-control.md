---
title: Birleşik giriş kutusu denetimine değer ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.combo
dev_langs:
- C++
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [Visual Studio], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- controls [C++], testing values in combo boxes
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c81e40de56970571ad78ceea86084b7ff7b82227
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="adding-values-to-a-combo-box-control"></a>Birleşik Giriş Kutusu Denetimine Değer Ekleme
Aç iletişim kutusu Düzenleyicisi olduğu sürece değerleri birleşik giriş kutusu denetimine ekleyebilirsiniz.  
  
> [!TIP]
>  Birleşik giriş kutusu tüm değerler eklemek için iyi bir fikirdir *önce* iletişim kutusu Düzenleyicisi kutusunda boyutu veya birleşik giriş denetiminde görüntülenmelidir metin kesmek.  
  
#### <a name="to-enter-values-into-a-combo-box-control"></a>Değerleri birleşik giriş kutusu denetimine girmek için  
  
1.  Birleşik giriş kutusu denetimi tıklayarak seçin.  
  
2.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), aşağı kaydırarak **veri** özelliği.  
  
    > [!NOTE]
    >  Türüne göre gruplandırılmış özellikleri görüntülüyorsanız **veri** görünür **çeşitli** özellikleri.  
  
3.  İçin değer alanında tıklatın **veri** özelliği ve türü, veri değerleri noktalı virgüllerle ayrılmış.  
  
    > [!NOTE]
    >  Aşağı açılan listesinde alfabetik hale getirme ile alanları engel olduğundan değerleri arasında boşluk koymayın.  
  
4.  Tıklatın **Enter** değerleri eklemeyi tamamladığınızda.  
  
 Birleşik giriş kutusu açılan kısmı büyütme hakkında daha fazla bilgi için bkz: [birleşik giriş kutusu ve ITS aşağı açılan listesinin boyutunu ayarlama](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).  
  
> [!NOTE]
>  Bu yordamı kullanarak Win32 projelere değerleri ekleyemezsiniz ( **veri** özelliği gri çıkışı Win32 projeleri için). Win32 projeleri bu özelliği eklemek kitaplıkları olmadığı için değerleri birleşik giriş kutusu Win32 Proje ile programlı olarak eklemeniz gerekir.  
  
#### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>Açılan kutuda değerlerinin görünümünü sınamak için  
  
1.  Değerleri girdikten sonra **veri** özelliği tıklatın **Test** düğmesini [iletişim kutusu Düzenleyicisi araç](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
     Tüm değer listede aşağı kaydırma deneyin. Değerleri görünür içinde tam olarak yazılmış şekilde **veri** Özellikleri penceresinde özelliği. Yazım veya büyük/küçük harf denetimi yoktur.  
  
     İletişim kutusu Düzenleyicisi'ne dönmek için ESC tuşuna basın.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimler](../mfc/controls-mfc.md)

