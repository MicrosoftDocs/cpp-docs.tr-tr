---
title: Bit eşlemleri araç çubuklarına (C++) dönüştürme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.newtoolbarresource
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor [C++], converting bitmaps
- toolbars [C++], converting bitmaps
- New Toolbar Resource dialog box [C++]
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
ms.openlocfilehash: 31b684ff72e970a6b09748b3925564b0b372d339
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702706"
---
# <a name="converting-bitmaps-to-toolbars-c"></a>Bit eşlemleri araç çubuklarına (C++) dönüştürme

Bir bit eşlem dönüştürerek bir C++ projesinde yeni bir araç çubuğu oluşturabilirsiniz. Bit eşlem Grafik araç çubuğu düğmesi görüntülerde dönüştürür. Genellikle her düğme için bir görüntü ile birkaç düğme resimlerini üzerinde tek bir bit eşlem bit eşlem içerir. Görüntüleri, herhangi bir boyutta olabilir; 16 piksel genişliğinde ve resmin yüksekliğini varsayılan değerdir. Düğme görüntüleri boyutunu belirtebilirsiniz **yeni araç çubuğu kaynağı** seçtiğinizde iletişim kutusu **araç çubuğu Düzenleyicisi** gelen **görüntü** Resim Düzenleyicisi sırada menüsünde.

**Yeni araç çubuğu kaynağı** iletişim kutusu, genişlik ve yükseklik bir C++ projesinde bir araç çubuğu kaynağı için eklediğiniz düğmelerinin belirtmenize olanak sağlar. Varsayılan değer 16 × 15 pikseldir.

Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 maksimum genişliği sahiptir. Bunu yaparsanız **düğmesi genişliği** 512, yalnızca dört düğme olabilir. Genişliği için 513 ayarlarsanız, yalnızca üç düğme olabilir.

İletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Düğme genişliği**|Araç çubuğu kaynak bit eşlem kaynağı dönüştürüyoruz araç çubuğu düğmeleri genişliğini girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.|
|**Düğme yüksekliği**|Araç çubuğu kaynak bit eşlem kaynağı dönüştürüyoruz araç çubuğu düğmeleri yüksekliği girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.|

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-convert-bitmaps-to-a-toolbar"></a>Bit eşlemleri araç çubuğuna dönüştürmek için

1. Mevcut bir bit eşlem kaynağındaki açın [Resim Düzenleyicisi](../windows/image-editor-for-icons.md). (Bit eşlem .rc dosyanızda değilse .rc dosyasına sağ tıklayın, seçin **alma** kısayol menüsünden, .rc dosyasına eklemek istediğiniz bit eşlem gidin ve ardından **açık**.)

1. Gelen **görüntü** menüsünde seçin **araç çubuğu Düzenleyicisi**.

   **Yeni araç çubuğu kaynağı** iletişim kutusu görüntülenir. Genişlik ve yükseklik simgesi görüntülerin bit eşlem eşleşecek şekilde değiştirebilirsiniz. Araç çubuğu görüntüsü, ardından araç çubuğu Düzenleyicisi'nde görüntülenir.

1. Dönüştürme işlemini tamamlamak için komutu değiştirmek **kimliği** düğmesini kullanarak [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Yeni tür **kimliği** veya bir **kimliği** aşağı açılan listeden.

   > [!TIP]
   > **Özellikleri** pencere bir başlık çubuğundaki Raptiye düğme içerir. Bu düğmeyi seçerek etkinleştirir veya devre dışı bırakır **Otomatik Gizle** penceresi. Tek tek özellik windows yeniden gerek kalmadan hızla tüm araç çubuğu düğmesi özellikleri geçiş yapmak için kapatma **Otomatik Gizle** kapalı böylece **özellikleri** penceresi sabit kalır.

Yeni araç çubuğundaki düğmeler komut kimlikleri kullanarak da değiştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Yeni araç çubuğu düzenleme hakkında daha fazla bilgi için bkz. [oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Yeni Araç Çubukları Oluşturma](../windows/creating-new-toolbars.md)<br/>
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)<br/>
[Araç Çubuğu Düğmesi Özellikleri](../windows/toolbar-button-properties.md)<br/>
