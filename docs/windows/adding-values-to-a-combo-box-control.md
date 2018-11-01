---
title: Birleşik Giriş Kutusu Denetimine Değer Ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [C++], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
ms.openlocfilehash: 5df37a14809a41166b713f946b4f1abc19ea1ff4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570384"
---
# <a name="adding-values-to-a-combo-box-control"></a>Birleşik Giriş Kutusu Denetimine Değer Ekleme

Sahip olduğunuz sürece bir birleşik giriş kutusu denetimine değer ekleyebilirsiniz **iletişim** Düzenleyicisi'ni açın.

> [!TIP]
> Açılan kutu tüm değerler eklemek için iyi bir fikirdir *önce* kutuya boyut **iletişim** Düzenleyicisi veya birleşik giriş denetiminde görüntülenecek metin kesin.

### <a name="to-enter-values-into-a-combo-box-control"></a>Bir birleşik giriş kutusu denetimine değer girmek için

1. Birleşik giriş kutusu denetimine tıklayarak seçin.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ekranı aşağı kaydırarak **veri** özelliği.

   > [!NOTE]
   > Türüne göre gruplandırılmış bir özellikler görüntülüyorsanız **veri** görünür **çeşitli** özellikleri.

3. Değer alanı için tıklatın **veri** özelliği ve türü, veri değerleri noktalı virgülle ayrılmış.

   > [!NOTE]
   > Aşağı açılan listesinde alfabetik hale getirme ile alanları müdahale çünkü değerleri arasında boşluk koymayın.

4. Tıklayın **Enter** değerleri eklemeyi tamamladığınızda.

Bir açılan kutunun açılır bölümünü genişleterek hakkında daha fazla bilgi için bkz: [birleşik giriş kutusu ve kendi aşağı açılan listesinin boyutunu ayarlama](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).

> [!NOTE]
> Bu yordamı kullanarak Win32 projeleri için değerleri eklenemiyor ( **veri** özelliği gri Win32 projeleri için). Win32 projeleri bu özelliği eklemek kitaplıkları olmadığı için değerleri bir Win32 projesi içeren bir birleşik giriş kutusu için programlı olarak eklemeniz gerekir.

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>Açılan kutuda değerleri görünümünü test etmek için

1. Değerleri girdikten sonra **veri** özelliği tıklayın **Test** düğmesini [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

   Tüm değer listede aşağı kaydırma deneyin. Değerlerin göründüğü içinde tam olarak yazdığınız şekilde **veri** özelliğinde **özellikleri** penceresi. Yazım denetimi veya büyük/küçük harf denetimi yoktur.

   Tuşuna **Esc** dönmek için **iletişim kutusu** Düzenleyici.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)