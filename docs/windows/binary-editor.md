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
ms.openlocfilehash: 420c5ecf44f8e8b264d9eafd93de58c0db3bedf4
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210724"
---
# <a name="binary-editor-c"></a>Binary Editor (C++)

> [!CAUTION]
> İletişim kutuları, resimler veya menülerde gibi kaynakları düzenleme **ikili düzenleyici** tehlikelidir. Yanlış düzenleme, kendi yerel düzenleyicisinde okunmaz hale gelir bir kaynak bozuk olabilir.

**İkili düzenleyici** onaltılık veya ASCII biçiminde ikili düzeyde herhangi bir kaynağa düzenlemenizi sağlar. Ayrıca [Bul komut](/visualstudio/ide/reference/find-command) ASCII dizelerinde veya onaltılık baytlar için aranacak. Kullanım **ikili düzenleyici** yalnızca özel kaynaklar veya kaynak türleri Visual Studio ortamı tarafından desteklenmeyen görüntülemek veya küçük gerektiğinde değiştirir.

Açmak için **ikili düzenleyici** yeni bir dosya menüsüne gidin **dosya** > **yeni** > **dosya**, türünü seçin Dosya düzenleme ardından yanındaki açılan oku seçerek **açık** düğmesini ve ardından **birlikte Aç** > **ikili düzenleyici**.

Açmak için **ikili düzenleyici** varolan bir dosyanın, menüsüne gidin **dosya** > **açın** > **dosya**seçin Dosya düzenleme ardından yanındaki açılan oku seçerek **açık** düğmesini ve ardından **birlikte Aç** > **ikili düzenleyici**.

   ![İkili Düzenleyici](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
   Görüntülenen iletişim kutusu için ikili verileri **İkili Düzenleyici**

Yalnızca belirli ASCII değerleri temsil edildiğini **ikili düzenleyici** (0x20 0x7E aracılığıyla). Genişletilmiş karakterler, nokta sağ panelde ASCII değeri bölümünde görüntülenir **ikili düzenleyici**. Yazdırılabilir karakter ASCII 32 126-değerlerdir.

> [!TIP]
> Kullanırken **ikili düzenleyici**, çoğu durumda bir kaynağa özgü komutların kısayol menüsünü görüntülemek için sağ tıklayabilirsiniz. Kullanılabilir komutlar ne imlecinizi işaret ettiği üzerinde bağlıdır. Örneğin işaret ederken tıklarsanız **ikili düzenleyici** ile seçilen onaltılı değerler, kısayol menüsünü gösterir **Kes**, **kopyalama**, ve **Yapıştır**  komutları.

**İkili düzenleyici** Express sürümlerinde kullanılamaz.

## <a name="how-to"></a>Nasıl Yapılır

**İkili düzenleyici** sağlar:

### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>İkili düzenleme için bir Windows Masaüstü kaynağını açmak için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.

1. Kaynak sağ tıklayıp **açık ikili veri**.

> [!NOTE]
> Kullanırsanız [kaynak görünümü](../windows/resource-view-window.md) tanımadığı Visual Studio, bir biçime bir kaynak penceresini RCDATA veya özel bir kaynak gibi kaynak otomatik olarak açılır **ikili düzenleyici**.

### <a name="to-open-a-managed-resource-for-binary-editing"></a>İkili düzenleme için bir yönetilen kaynak açmak için

1. İçinde **Çözüm Gezgini**, düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.

1. Kaynak sağ tıklayıp **birlikte Aç**.

1. İçinde **birlikte Aç** iletişim kutusunda **ikili düzenleyici**.

> [!NOTE]
> Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve **ikili düzenleyici** yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

### <a name="to-edit-a-resource"></a>Bir kaynak düzenlemek için

> [!NOTE]
> Kullanmak istiyorsanız **ikili düzenleyici** zaten başka bir düzenleyici penceresinde düzenlenmekte olan bir kaynakta önce diğer düzenleyici penceresini kapatın.

1. Düzenlemek istediğiniz bayt seçin.

   **Sekmesini** anahtar onaltılık ve ASCII bölümleri arasında odağı taşır **ikili düzenleyici**. Kullanabileceğiniz **Page Up** ve **Page Down** anahtarları kaynak bir ekran ilerlemek için.

1. Yeni bir değer girin.

   Hem onaltılık hem de ASCII bölümleri hemen değeri değiştirir ve sonraki satır değeri kaydırır.

> [!NOTE]
> **İkili düzenleyici** düzenleyicisini kapatırken değişiklikleri otomatik olarak kabul eder.

### <a name="to-find-binary-data"></a>İkili verileri bulmak için

ASCII dizelerinde veya onaltılık baytlar için arama yapabilirsiniz. Örneğin, bulma için *Hello*, için ya da dize arama yapabilirsiniz *Hello* ya da onaltılık değerini *48 65 6C 6 C 6F*.

1. Gelen **Düzenle** menüsünde seçin [Bul](/visualstudio/ide/reference/find-command).

1. İçinde **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya bulmak istediğiniz veri türü.

1. Herhangi bir **Bul** seçenekleri ve seçin **Sonrakini Bul**.

### <a name="to-create-a-new-custom-or-data-resource"></a>Yeni bir özel veya veri kaynağı oluşturmak için

Kaynak normal kaynak betiği (.rc) dosyası sözdizimi kullanılarak ayrı bir dosyada ve bu dosyayı içeren projenize sağ tıklayarak girerek yeni bir özel veya veri kaynağı oluşturabilirsiniz **Çözüm Gezgini** ve seçme **Kaynak içerikleri**.

1. [Bir .rc dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md) , özel veya veri kaynağı içeriyor.

   Null ile sonlandırılmış tırnak içine alınmış dizeler veya ondalık, onaltılık veya sekizlik biçimde tamsayılar olarak bir .rc dosyasında özel veri yazabilirsiniz.

1. İçinde **Çözüm Gezgini**, projenizin .rc dosyasını sağ tıklatın ve seçin **kaynak içerikleri**.

1. İçinde **derleme zamanı yönergeleri** kutusuna bir `#include` özel kaynağınızın örneğin içeren dosyanın adını verir deyimi:

    ```cpp
    #include mydata.rc
    ```

   Ne tür, yazım ve söz dizimi doğru olduğundan emin olun. İçeriğini **derleme zamanı yönergeleri** kutusunu tam olarak yazdığınız sırada kaynak betik dosyasına eklenir.

1. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

Özel bir kaynak oluşturmak için başka bir yolu ise özel kaynak olarak bir dış dosya içeri aktarmak için bkz: [nasıl yapılır: Kaynakları yönetmek](../windows/how-to-import-and-export-resources.md).

> [!NOTE]
> Yeni özel veya veri kaynakları oluşturmak için Win32 gerekir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)