---
title: Bir iletişim kutusu (C++) tasarlama
ms.date: 11/04/2016
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
ms.openlocfilehash: 4a879f6bb1cdcd4b4897e510fb21d04500dfd3f2
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742693"
---
# <a name="designing-a-dialog-box-c"></a>Bir iletişim kutusu (C++) tasarlama

Boyutu ve bir C++ iletişim kutusunda, konumu ve denetimleri içindeki boyutunu ve konumunu iletişim birimleriyle ölçülür. Visual Studio durum seçtiğiniz zaman çubuğunda sağ alt köşesindeki değerleri tek tek denetimler ve iletişim kutusu görünür.

Bir iletişim kutusu tasarlarken benzetimini gerçekleştirmek ve programınızı derlemeden çalışma zamanı davranışını sınama. Bu modda şunları yapabilirsiniz:

- Bir metin yazın, birleşik giriş kutusu listelerinden seçin, seçeneklerini açıp kapatabilir ve komutları seçin.

- Sekme sırasını test edin.

- Radyo düğmeleri ve onay kutuları gibi gruplandırmalarını test edin.

- İletişim kutusundaki denetimlerin klavye kısayollarını test.

   > [!NOTE]
   > Sihirbazları kullanarak yapılan iletişim kutusu kodu bağlantıları benzetime dahil edilmez.

Bir iletişim kutusunu test ettiğinizde, genellikle ana program penceresiyle ilişkili bir konumda görüntüler. İletişim kutusunun ayarladıysanız **mutlak hizalama** özelliğini **True**, ekranın sol üst köşesine göre olan konumda iletişim kutusunu görüntüler.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index).

## <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>İletişim kutusunun boyutunu ve konumunu belirtmek için

İçinde ayarlayabilirsiniz üç özellik [Özellikler penceresi](/visualstudio/ide/reference/properties-window) bir iletişim kutusu ekran görüneceği yeri belirtmek için. **Merkezi** özelliğidir; Boole değeri ayarlamanız **True**, iletişim kutusunda her zaman ekranın ortasında görünür. Ayarlarsanız **False**, ardından ayarlayabilirsiniz **XPos** ve **YPos** ekranda olduğunda iletişim kutusu görünür açıkça tanımlamak için özellikleri. Sol üst köşesinde olarak tanımlanan görüntüleme alanının sapma değerlerini konumu özelliklerdir `{X=0, Y=0}`. Konumu de bağlıdır **mutlak hizalama** özelliği: varsa **True**, ekrana göreli; koordinatları, **False**, iletişim göreli koordinatları Sahibin penceresi.

## <a name="to-test-a-dialog-box"></a>Bir iletişim kutusu test etmek için

1. Zaman **iletişim** Düzenleyicisi etkin pencere menü çubuğunda, seçin **biçimi** > **Test iletişim**.

1. Benzetimi bitirmek için basın **Esc**, veya yalnızca seçin **Kapat** test iletişim kutusu düğmesi.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[İletişim Kutusu Araç Çubuğunu Gösterme veya Gizleme](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)