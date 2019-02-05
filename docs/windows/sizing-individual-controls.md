---
title: Boyutlandırma denetimleri
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
- Make Same Size command
- combo boxes, sizing
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
ms.openlocfilehash: a6381dcf1aeb9f73ac3b656229d9332df2a6a519
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742719"
---
# <a name="sizing-controls"></a>Boyutlandırma denetimleri

Bir denetimi yeniden boyutlandırmak için boyutlandırma tutamaçlarını kullanın. İşaretçi boyutlandırma tutamacı konumlandırıldığında Şekil Denetimi boyutlandırılabilir yönergeleri belirtmek için değiştirir. Etkin boyutlandırma tutamaçlarını düz; boyutlandırma tutamacı boş ise, bu eksen boyunca denetimi yeniden boyutlandırılamaz.

Denetim kılavuzları veya kenar boşlukları yaslama tarafından bir denetimin boyutunu değiştirebilirsiniz ya da taşıyarak bir denetim ve başka bir kılavuzu yaslanan.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-size-an-individual-control"></a>Tek bir denetim boyutu

1. Denetimi seçin.

1. Denetimin boyutunu değiştirmek için boyutlandırma tutamaçlarını sürükleyerek:

   - Boyutlandırma üstünde ve kenarlar, yatay veya dikey boyutunu değiştirin.

   - Boyutlandırma köşelere yatay ve dikey boyutunu değiştirin.

   > [!TIP]
   > Basılı tutarak bir kerede denetimi bir iletişim birim (DLU) boyutlandırabilirsiniz **Shift** anahtar ve kullanarak **sağ ok** ve **aşağı ok** anahtarları.

## <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Denetim içindeki metnin sığması için otomatik olarak boyutlandırmak için

Seçin **içerik boyutu** gelen **biçimi** menüsü.

\- veya -

Denetime sağ tıklayın ve seçin **içerik boyutu** kısayol menüsünden.

## <a name="to-make-controls-the-same-width-height-or-size"></a>Aynı genişliğe, yüksekliğe veya boyuta denetimleri yapma

Baskın denetimi boyutuna göre Denetim grubunun yeniden boyutlandırabilirsiniz.

1. [Denetimleri seçin](../windows/selecting-multiple-controls.md) yeniden boyutlandırmak istediğiniz.

   Bu serideki ilk Seçili denetim baskın bir denetimdir. Grup denetimleri son boyutu baskın denetimi boyutuna bağlıdır. Baskın denetimi seçme hakkında daha fazla bilgi için bkz. [baskın denetimi belirtme](../windows/specifying-the-dominant-control.md).

1. Gelen **biçimi** menüsünde seçin **aynı boyutta yapın**, ardından aşağıdaki komutlardan birini seçin:

   - **Her ikisi de**

   - **Yükseklik**

   - **Genişlik**

## <a name="to-set-the-size-of-the-combo-box-and-its-drop-down-list"></a>Boyutu birleşik giriş kutusu ve aşağı açılan listesinin ayarlamak için

İletişim kutusuna eklediğinizde bir birleşik giriş kutusu boyutlandırabilirsiniz. Aşağı açılan liste kutusunda boyutunu belirtebilirsiniz. Daha fazla bilgi için [değerleri birleşik giriş kutusu denetimi ekleme](../windows/adding-values-to-a-combo-box-control.md).

### <a name="to-size-a-combo-box"></a>Boyutuna bir birleşik giriş kutusu

1. Birleşik giriş kutusu denetimi sizin iletişim kutunuzda seçin.

   Başlangıçta, yalnızca sağ ve sol boyutlandırma tutamaçlarını etkindir.

1. Birleşik giriş kutusunun genişliğini ayarlamak için boyutlandırma tutamaçlarını kullanın.

Ayrıca, birleşik giriş kutusunun yanıdaki açılan kısmı dikey boyutunu ayarlayabilirsiniz.

### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>Aşağı açılan liste kutusunda açılan boyutunu ayarlamak için

1. Birleşik giriş kutusunun sağındaki açılan ok düğmesini seçin.

   ![Bir MFC projesinde bir birleşik giriş kutusu oku](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   Genişletilmiş açılır listede alanı ile birleşik giriş kutusunun boyutunu göstermek için Denetim değişikliklerin anahattı.

1. Alt boyutlandırma tutamacı açılır listede alanın başlangıç boyutunu değiştirmek için kullanın.

   ![Birleşik giriş&#45;kutusu boyutlandırma MFC projesinde](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

1. Birleşik giriş kutusundaki açılır listede bölümünü yeniden kapatmak için açılan oku seçin.

## <a name="to-set-the-width-of-a-horizontal-scroll-bar-and-make-it-appear"></a>Yatay kaydırma çubuğunun genişliğini ayarlama ve görünmesini sağlamak için

MFC sınıfları kullanarak iletişim kutusuna bir yatay kaydırma çubuğu içeren bir liste kutusu eklediğinizde, kaydırma çubuğu uygulamanızı otomatik olarak görünmez.

Çağırarak geniş öğesi için bir maksimum genişliğini ayarlamak [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) kodunuzda.

   Bu değer kümesi kaydırma çubuğu görünmez, hatta öğeleri liste kutusunda kutudan daha geniş olduğunda.
> [!NOTE]
> Yatay kaydırma çubuğunun MFC gerektirir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
