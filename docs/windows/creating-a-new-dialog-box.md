---
title: 'Nasıl yapılır: Oluştur iletişim kutusu (C++)'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
- modal dialog boxes [C++], logon screens
- logon screens
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
ms.openlocfilehash: c757c82978a5107374e6de2f8cff24319ed64f9c
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336481"
---
# <a name="how-to-create-a-dialog-box-c"></a>Nasıl yapılır: Oluştur iletişim kutusu (C++)

Boyutu ve bir C++ iletişim kutusunda, konumu ve denetimleri içindeki boyutunu ve konumunu iletişim birimleriyle ölçülür. Visual Studio durum seçtiğiniz zaman çubuğunda sağ alt köşesindeki değerleri tek tek denetimler ve iletişim kutusu görünür.

Bir iletişim kutusu tasarlarken benzetimini gerçekleştirmek ve programınızı derlemeden çalışma zamanı davranışını sınama. Bu modda şunları yapabilirsiniz:

- Bir metin yazın, birleşik giriş kutusu listelerinden seçin, seçeneklerini açıp kapatabilir ve komutları seçin.

- Sekme sırasını test edin.

- Radyo düğmeleri ve onay kutuları gibi gruplandırmalarını test edin.

- İletişim kutusundaki denetimlerin klavye kısayollarını test.

   > [!NOTE]
   > Sihirbazları kullanarak yapılan iletişim kutusu kodu bağlantıları benzetime dahil edilmez.

Bir iletişim kutusunu test ettiğinizde, genellikle ana program penceresiyle ilişkili bir konumda görüntüler. İletişim kutusunun ayarladıysanız **mutlak hizalama** özelliğini **True**, ekranın sol üst köşesine göre olan konumda iletişim kutusunu görüntüler.

## <a name="to-create-a-new-dialog-box"></a>Yeni iletişim kutusu oluşturmak için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde **kaynak Ekle** iletişim kutusunda **iletişim** içinde **kaynak türü** listeleyin ve ardından **yeni**.

   Bir artı işareti (**+**) yanında görünen **iletişim** kaynak türü geldiğini iletişim kutusu şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin veya seçmek için artı işaretini seçin **yeni**.

   Yeni iletişim kutusu açılır **iletişim** Düzenleyici.

   Ayrıca [mevcut iletişim kutuları iletişim kutusu düzenleyicisinde düzenlemek üzere açın](../windows/viewing-and-editing-resources-in-a-resource-editor.md).

## <a name="to-create-a-dialog-box-that-a-user-cant-exit"></a>Bir kullanıcı çıkamayacağı iletişim kutusu oluşturmak için

Bir kullanıcı çıkamayacağı bir çalışma zamanı iletişim kutusu oluşturabilirsiniz. Bu tür bir iletişim kutusu, oturum açma ve uygulama veya belge kilit için kullanışlıdır.

1. İçinde **özellikleri** iletişim kutusu için bölmesinde **sistem menüsü** özelliğini **false**.

   Bu ayar iletişim kutusu sistem menüsü devre dışı bırakır ve **Kapat** düğmesi.

1. İletişim kutusu formda Sil **iptal** ve **Tamam** düğmeleri.

   Çalışma zamanında, bir kullanıcı bu özelliklere sahip bir modal iletişim kutusu çıkamayacağı.

İletişim kutusunun bu tür bir testi etkinleştirmek için test iletişim kutusu işlevi zaman algılar **Esc** basıldığında. (**Esc** de VK_ESCAPE sanal anahtar denir.) Nasıl iletişim kutusunda çalışma zamanında davranacak şekilde tasarlanmış ne olursa olsun, test modu tuşlarına basarak sona erdirebilirsiniz **Esc**.

> [!NOTE]
> MFC uygulamaları için kullanıcıların çıkamayacağı, bir iletişim kutusu oluşturmak için varsayılan davranışı geçersiz kılmanız gerekir `OnOK` ve `OnCancel` ilişkili düğmeleri silseniz bile iletişim kutusunun hala tuşlarına basarak kapatılabilir çünkü  **Girin** veya **Esc**.

## <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>İletişim kutusunun boyutunu ve konumunu belirtmek için

İçinde ayarlayabilirsiniz üç özellik [Özellikler penceresi](/visualstudio/ide/reference/properties-window) bir iletişim kutusu ekran görüneceği yeri belirtmek için. **Merkezi** özelliğidir; Boole değeri ayarlamanız **True**, iletişim kutusunda her zaman ekranın ortasında görünür. Ayarlarsanız **False**, ardından ayarlayabilirsiniz **XPos** ve **YPos** ekranda olduğunda iletişim kutusu görünür açıkça tanımlamak için özellikleri. Sol üst köşesinde olarak tanımlanan görüntüleme alanının sapma değerlerini konumu özelliklerdir `{X=0, Y=0}`. Konumu de bağlıdır **mutlak hizalama** özelliği: varsa **True**, ekrana göreli; koordinatları, **False**, iletişim göreli koordinatları Sahibin penceresi.

## <a name="to-test-a-dialog-box"></a>Bir iletişim kutusu test etmek için

1. Zaman **iletişim** Düzenleyicisi etkin pencere menü çubuğunda, seçin **biçimi** > **Test iletişim**.

1. Benzetimi bitirmek için basın **Esc** veya **Kapat** test iletişim kutusu düğmesi.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Kaynak Oluşturma](../windows/how-to-create-a-resource.md)<br/>
[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>