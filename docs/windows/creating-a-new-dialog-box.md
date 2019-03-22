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
ms.openlocfilehash: 7e7cfcc206ce58ab401bcdb9c9ac6103c50e997f
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328642"
---
# <a name="how-to-create-a-dialog-box-c"></a>Nasıl yapılır: Oluştur iletişim kutusu (C++)

Boyutu ve bir C++ iletişim kutusunda, konumu ve denetimleri içindeki boyutunu ve konumunu iletişim birimleriyle ölçülür. Visual Studio durum seçtiğiniz zaman çubuğunda sağ alt köşesindeki değerleri tek tek denetimler ve iletişim kutusu görünür.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="how-to"></a>Nasıl Yapılır

**İletişim kutusu Düzenleyicisi** sağlar:

### <a name="to-create-a-new-dialog-box"></a>Yeni iletişim kutusu oluşturmak için

1. İçinde [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), sağ tıklayın, *.rc* seçin ve dosya **kaynak Ekle**.

1. İçinde **kaynak Ekle** iletişim kutusunda **iletişim** içinde **kaynak türü** listeleyin ve ardından **yeni**.

   Bir artı işareti (**+**) yanında görünen **iletişim** kaynak türü geldiğini iletişim kutusu şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin veya seçmek için artı işaretini seçin **yeni**.

   Yeni iletişim kutusu açılır **iletişim kutusu Düzenleyicisi**.

Düzenleme için iletişim kutusu Düzenleyicisi'nde mevcut iletişim kutuları da açabilirsiniz.

### <a name="to-create-a-dialog-box-that-a-user-cant-exit"></a>Bir kullanıcı çıkamayacağı iletişim kutusu oluşturmak için

Bir kullanıcı çıkamayacağı bir çalışma zamanı iletişim kutusu oluşturabilirsiniz. Bu tür bir iletişim kutusu, oturum açma ve uygulama veya belge kilit için kullanışlıdır.

1. İçinde **özellikleri** iletişim kutusu için bölmesinde **sistem menüsü** özelliğini **false**.

   Bu ayar iletişim kutusu sistem menüsü devre dışı bırakır ve **Kapat** düğmesi.

1. İletişim kutusu formda Sil **iptal** ve **Tamam** düğmeleri.

   Çalışma zamanında, bir kullanıcı bu özelliklere sahip bir modal iletişim kutusu çıkamayacağı.

İletişim kutusunun bu tür bir testi etkinleştirmek için test iletişim kutusu işlevi zaman algılar **Esc** basıldığında. **ESC** de VK_ESCAPE sanal anahtar denir. Nasıl iletişim kutusunda çalışma zamanında davranacak şekilde tasarlanmış ne olursa olsun, test modu tuşlarına basarak sona erdirebilirsiniz **Esc**.

> [!NOTE]
> MFC uygulamaları için kullanıcıların çıkamayacağı, bir iletişim kutusu oluşturmak için varsayılan davranışı geçersiz kılmanız gerekir `OnOK` ve `OnCancel` ilişkili düğmeleri silseniz bile iletişim kutusunun hala tuşlarına basarak kapatılabilir çünkü  **Girin** veya **Esc**.

### <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>İletişim kutusunun boyutunu ve konumunu belirtmek için

İçinde ayarlanan özellikler vardır [Özellikler penceresi](/visualstudio/ide/reference/properties-window) bir iletişim kutusu ekran görüneceği yeri belirtmek için.

- Boolean **Merkezi** özelliği.

   Değeri ayarlamanız **True**, iletişim kutusunda her zaman ekranın ortasında görünür. Bu özelliği ayarlamak, **False**, ardından ayarlayabilirsiniz **XPos** ve **YPos** özellikleri.

- **XPos** ve **YPos** ekran burada açıkça tanımlamak için kullanılan özellikleri iletişim kutusu görüntülenir.

   Bu konumu sol üst köşesinde olarak tanımlanan görüntüleme alanının sapma değerlerini özelliklerdir `{X=0, Y=0}`.

- **Mutlak hizalama** konumunu etkileyen özelliği.

   Varsa **True**, ekrana göreli koordinatları. Varsa **False**, iletişim sahibinin penceresiyle ilişkili koordinatlar belirlenir.

### <a name="to-test-a-dialog-box"></a>Bir iletişim kutusu test etmek için

Bir iletişim kutusu tasarlarken benzetimini gerçekleştirmek ve programınızı derlemeden çalışma zamanı davranışını sınama. Bu modda şunları yapabilirsiniz:

- Bir metin yazın, birleşik giriş kutusu listelerinden seçin, seçeneklerini açıp kapatabilir ve komutları seçin.

- Sekme sırasını test edin.

- Radyo düğmeleri ve onay kutuları gibi gruplandırmalarını test edin.

- İletişim kutusundaki denetimlerin klavye kısayollarını test.

> [!NOTE]
> Sihirbazları kullanarak yapılan iletişim kutusu kodu bağlantıları benzetime dahil edilmez.

Bir iletişim kutusunu test ettiğinizde, genellikle ana program penceresiyle ilişkili bir konumda görüntüler. İletişim kutusu ayarladıysanız **mutlak hizalama** özelliğini **True**, ekranın sol üst köşesine göre olan konumda iletişim kutusunu görüntüler.

1. Zaman **iletişim kutusu Düzenleyicisi** menüsüne gidin etkin pencere **biçimi** > **Test iletişim**.

1. Benzetimi bitirmek için basın **Esc** veya **Kapat** test iletişim kutusu düğmesi.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[Nasıl yapılır: İletişim kutusu denetimleri yönetme](../windows/controls-in-dialog-boxes.md)<br/>