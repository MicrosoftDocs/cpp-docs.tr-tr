---
title: Binary Editor (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.binary.F1
- vc.editors.binary
helpviewer_keywords:
- editors, Binary
- resources [C++], editing
- resource editors [C++], Binary editor
- Binary editor
- binary data, editing
- resources [C++], opening for binary editing
- binary data
- hexadecimal bytes in binary data
- strings [C++], searching for
- file searches [C++]
- binary data, finding
- ASCII characters, finding in binary data
- custom resources [C++]
- data resources [C++]
- resources [C++], creating
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
ms.openlocfilehash: 2a3ff3d89c809f57ea3ddbd70d5664fc8d13cec4
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320828"
---
# <a name="binary-editor-c"></a>Binary Editor (C++)

> [!WARNING]
> **İkili düzenleyici** Express sürümlerinde kullanılamaz.

İkili Düzenleyicisi onaltılık veya ASCII biçiminde ikili düzeyde herhangi bir kaynağa düzenlemenizi sağlar. Ayrıca [Bul komut](/visualstudio/ide/reference/find-command) ASCII dizelerinde veya onaltılık baytlar için aranacak. Kullanmanız gereken **ikili** görüntülemek veya küçük yapmak yalnızca ihtiyacınız olduğunda Düzenleyicisi değişiklikleri özel kaynaklar veya kaynak türleri Visual Studio ortamı tarafından desteklenmiyor.

Açmak için **ikili düzenleyici**, ilk seçin **dosya** > **yeni** > **dosya** ana menüden Dosya düzenleme ardından yanındaki açılan oku seçerek **açık** düğmesini ve ardından **birlikte Aç** > **ikili düzenleyici**.

> [!CAUTION]
> İletişim kutuları, resimler veya ikili düzenleyicide menüler gibi kaynakları düzenleme tehlikelidir. Yanlış düzenleme, kendi yerel düzenleyicisinde okunmaz hale gelir bir kaynak bozuk olabilir.

![İkili Düzenleyici](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
İkili veriler için ikili dosya Düzenleyicisi'nde görüntülenen iletişim kutusu

Yalnızca belirli ASCII değerleri (0x20 0x7E aracılığıyla) ikili düzenleyicide temsil edilir. Genişletilmiş karakterler, nokta İkili Düzenleyicisi (sağ panelde) ASCII değeri bölümünde görüntülenir. "Yazdırılabilir" karakterleri ASCII 32 126-değerlerdir.

> [!TIP]
> Kullanırken **ikili** düzenleyicisinde birçok örneği sağ kaynağa özgü komutların kısayol menüsü görüntülenecek. Kullanılabilir komutlar ne imlecinizi işaret ettiği üzerinde bağlıdır. Örneğin, işaret ederken tıklarsanız **ikili** seçili onaltılık değerler düzenleyicisinde, kısayol menüsünü gösterir **Kes**, **kopyalama**, ve **Yapıştır**  komutları.

## <a name="how-to"></a>Nasıl Yapılır Konuları

**İkili** Düzenleyicisi sağlar:

### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>İkili düzenleme için bir Windows Masaüstü kaynağını açmak için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.

1. Kaynak sağ tıklatıp **açık ikili veri** kısayol menüsünden.

   > [!NOTE]
   > Kullanırsanız [kaynak görünümü](../windows/resource-view-window.md) Visual Studio (RCDATA veya özel bir kaynak gibi), kaynak tanımıyor, biçimi ile bir kaynak penceresini açık otomatik olarak **ikili** Düzenleyici.

### <a name="to-open-a-managed-resource-for-binary-editing"></a>İkili düzenleme için bir yönetilen kaynak açmak için

1. İçinde **Çözüm Gezgini**, düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.

1. Kaynak sağ tıklatın ve seçin **birlikte Aç** kısayol menüsünden.

1. İçinde **birlikte Aç** iletişim kutusunda **ikili düzenleyici**.

   > [!NOTE]
   > Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

> [!NOTE]
> Kullanmak istiyorsanız **ikili** zaten başka bir düzenleyici penceresinde düzenlenmekte olan bir kaynak düzenleyicisini diğer düzenleyici penceresini önce kapatın.

### <a name="to-edit-a-resource"></a>Bir kaynak düzenlemek için

1. Düzenlemek istediğiniz bayt seçin.

   **Sekmesini** anahtar onaltılık ve ASCII bölümleri arasında odağı taşır **ikili** Düzenleyici. Kullanabileceğiniz **Page Up** ve **Page Down** anahtarları kaynak bir ekran ilerlemek için.

1. Yeni bir değer girin.

   Hem onaltılık hem de ASCII bölümleri hemen değeri değiştirir ve sonraki satır değeri kaydırır.

   > [!NOTE]
   > **İkili** Düzenleyicisi, düzenleyicisini kapatırken değişiklikleri otomatik olarak kabul eder.

### <a name="to-find-binary-data"></a>İkili verileri bulmak için

ASCII dizelerinde veya onaltılık baytlar için arama yapabilirsiniz. Örneğin, "Hello" bulmak için sizin için ya da dize "Hello" veya arayabilirsiniz "48 65 6C 6 C 6F" (onaltılık eşdeğeri).

1. Gelen **Düzenle** menüsünde seçin [Bul](/visualstudio/ide/reference/find-command).

1. İçinde **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya bulmak istediğiniz veri türü.

1. Herhangi bir **Bul** seçenekleri ve seçin **Sonrakini Bul**.

### <a name="to-create-a-new-custom-or-data-resource"></a>Yeni bir özel veya veri kaynağı oluşturmak için

Kaynak normal kaynak betiği (.rc) dosyası sözdizimi kullanılarak ayrı bir dosyada ve bu dosyayı içeren projenize sağ tıklayarak girerek yeni bir özel veya veri kaynağı oluşturabilirsiniz **Çözüm Gezgini** tıklayıp **Kaynak içeren** kısayol menüsünde.

1. [Bir .rc dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md) , özel veya veri kaynağı içeriyor.

   Null ile sonlandırılmış tırnak içine alınmış dizeler veya ondalık, onaltılık veya sekizlik biçimde tamsayılar olarak bir .rc dosyasında özel veri yazabilirsiniz.

1. İçinde **Çözüm Gezgini**, projenizin .rc dosyasını sağ tıklatın ve ardından **kaynak içerikleri** kısayol menüsünde.

1. İçinde **derleme zamanı yönergeleri** kutusuna bir `#include` özel kaynağınızı içeren dosyanın adını verir deyimi. Örneğin:

    ```cpp
    #include mydata.rc
    ```

   Ne tür, yazım ve söz dizimi doğru olduğundan emin olun. İçeriğini **derleme zamanı yönergeleri** kutusunu tam olarak yazdığınız şekilde kaynak betik dosyasına eklenir.

1. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

Özel bir kaynak oluşturmak için başka bir özel kaynak olarak bir dış dosya aktarmak için yoludur. Daha fazla bilgi için [alma ve verme kaynakları](../windows/how-to-import-and-export-resources.md).

> [!NOTE]
> Yeni özel veya veri kaynakları oluşturmak için Win32 gerekir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)