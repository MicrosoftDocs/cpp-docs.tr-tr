---
title: Dize Düzenleyicisi'ni (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.string.F1
- vc.editors.string
helpviewer_keywords:
- String editor
- string tables
- string tables [C++], String editor
- string editing
- string editing, string tables
- resource editors [C++], String editor
- strings [C++], editing
- strings [C++], searching
- strings [C++]
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
ms.openlocfilehash: 47d5835356863383b32baffc4475e01a652e9856
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387935"
---
# <a name="string-editor-c"></a>Dize Düzenleyicisi'ni (C++)

Dize tablosu kimlikleri, değerleri ve açıklamalı alt yazılar, uygulamanızın tüm dizeleri listesini içeren bir Windows kaynaktır. Örneğin, durum çubuğu komut istemlerini dize tablosunda yer alır.

Bir uygulama geliştirirken birden çok dize tabloları olabilir — her dilini veya koşulunu biri. Ancak, yalnızca bir dize tablosu bir çalıştırılabilir modüle sahiptir. Tabloları farklı dll koyarsanız çalışan bir uygulama birden çok dize tabloları başvurabilirsiniz.

Dize tabloları uygulamanızın farklı dillere yerelleştirilmesi kolaylaştırır. Tüm dizeler dize tablosunda, dizeleri (ve diğer kaynakları) kaynak kodunda değişiklik yapmadan çevirerek uygulama yerelleştirebilirsiniz. Bu durum, el ile dizeleri bulma ve çeşitli kaynak dosyalarında değiştirme daha fazla tercih edilir.

> [!NOTE]
> Windows, boş dize tabloları oluşturulmasına izin vermiyor. Dize tablosu giriş yok oluşturursanız, kaynak dosyasını kaydettiğinizde, otomatik olarak silinir.

## <a name="how-to"></a>Nasıl Yapılır

**Dize Düzenleyicisi** sağlar:

### <a name="to-find-a-string-resource-in-the-string-table"></a>Dize tablosunda bir dize kaynağı bulunamadı

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Menü Git **Düzenle** > **Bul ve Değiştir** ve **Bul**.

1. İçinde **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya bulmak istediğiniz string açıklamalı alt yazı metni ya da kaynak tanımlayıcı yazın.

1. Herhangi bir **Bul** seçenekleri ve select **Sonrakini Bul**.

> [!TIP]
> Kullanılacak [normal ifadeler](/visualstudio/ide/using-regular-expressions-in-visual-studio) dosyalarını ararken kullanmak **dosyalarda Bul** komutunu **Düzenle** menüsü.
>
> Sağındaki düğmeyi seçin veya bir desenle eşleşen normal bir ifade yazın **Aranan** normal arama listesini görüntülemek için kutusu. Bu listeden bir ifade seçtiğinizde, arama metni olarak geçmesidir **Aranan** kutusu.
>
> Normal ifadeler kullanırsanız, mutlaka **kullanın: Normal ifadeler** onay kutusu seçilidir.

### <a name="to-add-or-delete-a-string-resource"></a>Ekleme veya bir dize kaynağı silme

Hızlı ekleme veya silme kullanarak dize tablo girişleri **Dize Düzenleyicisi**. Yeni dizeler tablonun sonuna yerleştirilir ve sonraki kullanılabilir tanımlayıcı verilir. Düzenleyebileceğiniz **kimliği**, **değer**, veya **açıklamalı alt yazı** özelliklerinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window) gerektiğinde.

**Dize Düzenleyicisi** zaten kullanımda bir kimliği kullanmayın emin olur. Bir kimliği kullanımda, zaten seçerseniz **Dize Düzenleyicisi** bunu size bildirir ve ardından genel benzersiz kimliği örneğin Ata `IDS_STRING58113`.

#### <a name="to-add-a-string-table-entry"></a>Dize tablo girdisi eklemek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Dize tablosu içinde sağ tıklatın ve seçin **yeni dize**.

1. İçinde **Dize Düzenleyicisi**seçin bir **kimliği** gelen **kimliği** aşağı açılan liste veya türü bir *kimliği* doğrudan yerinde.

1. Düzen **değer**, gerekirse.

1. İçin bir giriş türü **açıklamalı alt yazı**.

   > [!NOTE]
   > Null dizeler Windows dize tablolarında izin verilmez. Boş bir dize olan dize tablosunda bir giriş oluşturmak, isteyen bir ileti alırsınız **Lütfen bu tablo girişi için bir dize girin**.

#### <a name="to-delete-a-string-table-entry"></a>Dize tablosu girişi silmek için

Aşağıdakilerden birini yapın ve silmek istediğiniz girişini seçin:

- Menü Git **Düzenle** > **Sil**.

- Silme ve dize sağ **Sil**.

- Tuşuna **Sil** anahtarı.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Bir dizeyi bir kaynak betik dosyasını diğerine taşımak için

1. [Dize tabloları her iki .rc dosyaları açmak](../windows/how-to-create-a-resource-script-file.md).

1. Taşıma ve dize sağ **Kes**.

1. Hedef imleci **Dize Düzenleyicisi** penceresi.

1. İçinde *.rc* dize taşımak, sağ tıklayın ve istediğiniz dosyayı **Yapıştır**.

> [!NOTE]
> Varsa **kimliği** veya **değer** ile varolan taşınan dize çakışmalar **kimliği** veya **değer** hedef dosyasında ya da bu **Kimliği** veya **değer** taşınan dize değişiklikleri.

### <a name="to-change-the-properties-of-a-string-resource"></a>Bir dize kaynağının özelliklerini değiştirmek için

Yerinde düzenleme değiştirmek için kullanabileceğiniz **kimliği**, **değer**, ve **açıklamalı alt yazı** özellikleri.

> [!NOTE]
>  Bir dizenin özelliklerini de düzenleyebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

#### <a name="to-change-a-string-or-its-identifier"></a>Bir dize veya tanımlayıcısını değiştirmek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Çift tıklayın ve düzenlemek istediğiniz dizeyi seçin **kimliği**, **değer**, veya **açıklamalı alt yazı** sütun sonra kullanabilirsiniz:

   - Seçin bir **kimliği** gelen **kimliği** aşağı açılan liste veya türü bir *kimliği* doğrudan yerinde.

   - Farklı bir sayı yazın **değer** sütun.

   - Tür düzenlemeleri **açıklamalı alt yazı** sütun.

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>Birden çok dize kaynakları resim yazısı özelliğini değiştirmek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Basılı tutarak değiştirmek istediğiniz dizeleri seçin **Ctrl** anahtar her birini seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), değiştirmek istediğiniz özelliği için yeni bir değer yazın.

1. Tuşuna **girin**.

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>Biçimlendirme veya özel karakterler için bir dize kaynağı eklemek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Değiştirmek istediğiniz dizeyi seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), herhangi bir standart kaçış dizileri aşağıda listelenen metinde ekleme **açıklamalı alt yazı** kutusuna yerleştirip **Enter**.

   |Bu alınacağı...|Bunu yazın...|
   |-----------------|---------------|
   | Yeni satır | \\N |
   | satır başı | \\r |
   | Tab | \\T |
   | Ters eğik çizgi (\\) | \\\\ |
   | ASCII karakteri | \\ddd (sekizlik gösterim) |
   | Uyarı (zil) | \\A |

   > [!NOTE]
   > **Dize Düzenleyicisi** kaçan ASCI karakter kümesini desteklemiyor. Yalnızca yukarıda listelenen kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)
<!--
[Strings](https://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)<br/>
[About Strings](/windows/desktop/menurc/about-strings)<br/>
[Customizing window layouts](/visualstudio/ide/customizing-window-layouts-in-visual-studio)-->