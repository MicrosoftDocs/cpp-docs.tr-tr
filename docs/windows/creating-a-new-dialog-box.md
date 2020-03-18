---
title: 'Nasıl yapılır: Iletişim kutusu oluşturma (C++)'
ms.date: 02/15/2019
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
ms.openlocfilehash: 380cf58180913f538c1c326d6aaf49947b694063
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445421"
---
# <a name="how-to-create-a-dialog-box-c"></a>Nasıl yapılır: Iletişim kutusu oluşturma (C++)

Bir C++ iletişim kutusunun konumu ve boyutu ve içindeki denetimlerin konumu ve boyutu iletişim kutusu birimlerinde ölçülür. Tek tek denetimlerin değerleri ve iletişim kutusu, siz seçtiğinizde Visual Studio durum çubuğunun sağ alt kısmında görünür.

> [!NOTE]
> Projeniz zaten bir. rc dosyası içermiyorsa, bkz. [Yeni kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="how-to"></a>Nasıl yapılır?

**Iletişim kutusu Düzenleyicisi** şunları yapmanızı mümkün:

### <a name="to-create-a-new-dialog-box"></a>Yeni bir iletişim kutusu oluşturmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyanıza sağ tıklayıp **Kaynak Ekle**' yi seçin.

1. **Kaynak Ekle** Iletişim kutusunda **kaynak türü** listesinden **diyalog** ' ı seçin ve ardından **Yeni**' yi seçin.

   **İletişim** kutusu kaynak türünün yanında bir artı işareti ( **+** ) görünürse, iletişim kutusu şablonlarının kullanılabildiği anlamına gelir. Şablon listesini genişletmek için artı işaretini seçin, bir şablon seçin ve **Yeni**' yi seçin.

   **İletişim kutusu düzenleyicisinde**yeni iletişim kutusu açılır.

Ayrıca, düzenleme için Iletişim kutusu düzenleyicisinde varolan iletişim kutularını da açabilirsiniz.

### <a name="to-create-a-dialog-box-that-a-user-cant-exit"></a>Kullanıcının çıkamayacağı bir iletişim kutusu oluşturmak için

Bir kullanıcının çıkamayacağı bir çalışma zamanı iletişim kutusu oluşturabilirsiniz. Bu tür iletişim kutusu, oturum açma işlemleri için ve uygulama veya belge kilitleri için kullanışlıdır.

1. İletişim kutusunun **Özellikler** bölmesinde, **Sistem menü** özelliğini **false**olarak ayarlayın.

   Bu ayar, iletişim kutusu sistem menüsünü ve **Kapat** düğmesini devre dışı bırakır.

1. İletişim kutusu formunda, **iptal** ve **Tamam** düğmelerini silin.

   Çalışma zamanında, bir Kullanıcı bu özelliklere sahip kalıcı bir iletişim kutusundan çıkamayacağı.

Bu tür bir iletişim kutusunun test edilmesini etkinleştirmek için, **ESC** tuşuna basıldığında test iletişim kutusu işlevi algılanır. **ESC** , vk_escape sanal anahtarı olarak da bilinir. İletişim kutusunun çalışma zamanında davranması için nasıl tasarlandığına bakılmaksızın **ESC**tuşuna basarak test modunu sona bırakabilirsiniz.

> [!NOTE]
> MFC uygulamalarında, kullanıcıların çıkamayacağı bir iletişim kutusu oluşturmak için, `OnOK` ve `OnCancel` varsayılan davranışını geçersiz kılmanız gerekir, çünkü ilişkili düğmeleri silseniz bile, iletişim kutusu **ENTER** veya **ESC**tuşuna basarak yine de kapatılabilir.

### <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>Bir iletişim kutusunun konumunu ve boyutunu belirtmek için

Bir iletişim kutusunun ekranda görüneceği yeri belirtmek için [Özellikler penceresinde](/visualstudio/ide/reference/properties-window) ayarlayabileceğiniz özellikler vardır.

- Boolean **Center** özelliği.

   Değeri **true**olarak ayarlarsanız, iletişim kutusu her zaman ekranın ortasında görüntülenir. Bu özelliği **false**olarak ayarlarsanız, **XPos** ve **enpos** özelliklerini ayarlayabilirsiniz.

- Açık olarak görüntülenen iletişim kutusunun görüneceği yeri açıkça tanımlamak için kullanılan **XPos** ve **enpos** özellikleri.

   Bu konum özellikleri, `{X=0, Y=0}`olarak tanımlanan, görüntüleme alanının sol üst köşesinden alınan değerlerdir.

- Konumu etkileyen **mutlak hizalama** özelliği.

   **Doğru**ise, koordinatlar ekrana görelidir. **Yanlışsa**, koordinatlar iletişim kutusu sahibinin penceresine görelidir.

### <a name="to-test-a-dialog-box"></a>Bir iletişim kutusunu test etmek için

Bir iletişim kutusu tasarlarken, programınızı derlemeden çalışma zamanı davranışının benzetimini yapabilir ve test edebilirsiniz. Bu modda şunları yapabilirsiniz:

- Metin yazın, Birleşik giriş kutusu listelerinden seçim yapın, seçenekleri açın veya kapatın ve komutlar ' ı seçin.

- Sekme sırasını test edin.

- Radyo düğmeleri ve onay kutuları gibi denetimlerin gruplandırmasını test edin.

- İletişim kutusunda denetimler için klavye kısayollarını test edin.

> [!NOTE]
> Sihirbazlar kullanılarak yapılan iletişim kutusu kodu bağlantıları simülasyonuna dahil değildir.

Bir iletişim kutusunu test ettiğinizde, genellikle ana program penceresine göreli bir konumda görüntülenir. İletişim kutusu **mutlak hizalama** özelliğini **doğru**olarak ayarladıysanız, iletişim kutusu ekranın sol üst köşesine göre bir konumda görüntülenir.

1. **Iletişim kutusu Düzenleyicisi** etkin pencere olduğunda, menü **biçimi** > **test iletişim kutusuna**gidin.

1. Benzetimi sonlandırmak için **ESC** tuşuna basın veya test ettiğiniz Iletişim kutusunda **Kapat** düğmesini seçin.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[Nasıl yapılır: Iletişim kutusu denetimlerini yönetme](../windows/controls-in-dialog-boxes.md)<br/>