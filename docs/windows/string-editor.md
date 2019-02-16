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
ms.openlocfilehash: 8f33ef6d0198f083e7cf1b1e1dc2129be9b3fab4
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320568"
---
# <a name="string-editor-c"></a>Dize Düzenleyicisi'ni (C++)

Dize tablosu kimlikleri, değerleri ve açıklamalı alt yazılar, uygulamanızın tüm dizeleri listesini içeren bir Windows kaynaktır. Örneğin, durum çubuğu komut istemlerini dize tablosunda yer alır.

Bir uygulama geliştirirken birden çok dize tabloları olabilir — her dilini veya koşulunu biri. Ancak, yalnızca bir dize tablosu bir çalıştırılabilir modüle sahiptir. Tabloları farklı dll koyarsanız çalışan bir uygulama birden çok dize tabloları başvurabilirsiniz.

Dize tabloları uygulamanızın farklı dillere yerelleştirilmesi kolaylaştırır. Tüm dizeler dize tablosunda, dizeleri (ve diğer kaynakları) kaynak kodunda değişiklik yapmadan çevirerek uygulama yerelleştirebilirsiniz. Bu durum, el ile dizeleri bulma ve çeşitli kaynak dosyalarında değiştirme daha fazla tercih edilir.

## <a name="how-to"></a>Nasıl Yapılır Konuları

Kullanım **dize** Düzenleyicisi aşağıdaki eylemleri için:

### <a name="to-find-a-string-resource-in-the-string-table"></a>Dize tablosunda bir dize kaynağı bulunamadı

Dize tablosunda bir veya daha fazla dizeleri arayın ve kullanmak [normal ifadeler](/visualstudio/ide/using-regular-expressions-in-visual-studio) ile **dosyalarda Bul** komut (**Düzenle** menüsü) dizeleri tüm örneklerini bulmak için bir desen eşleşmesi.

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Üzerinde **Düzenle** menüsünde **Bul ve Değiştir**, ardından **Bul**.

1. İçinde **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya bulmak istediğiniz string açıklamalı alt yazı metni ya da kaynak tanımlayıcı yazın.

1. Herhangi bir **Bul** seçenekleri.

1. Seçin **Sonrakini Bul**.

   > [!TIP]
   > Normal ifadeler dosya ararken kullanmak için **dosyalarda Bul** komutu. Sağındaki düğmeyi seçin veya bir desenle eşleşen normal bir ifade yazın **Aranan** normal arama listesini görüntülemek için kutusu. Bu listeden bir ifade seçtiğinizde, arama metni olarak geçmesidir **Aranan** kutusu. Normal ifadeler kullanırsanız, mutlaka **kullanın: Normal ifadeler** onay kutusu seçilidir.

### <a name="to-add-or-delete-a-string-resource"></a>Ekleme veya bir dize kaynağı silme

Hızlı ekleme veya silme kullanarak dize tablo girişleri **dize** Düzenleyici. Yeni dizeler tablonun sonuna yerleştirilir ve sonraki kullanılabilir tanımlayıcı verilir. Daha sonra düzenleyebilirsiniz **kimliği**, **değer**, veya **açıklamalı alt yazı** özelliklerinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window) gerektiğinde.

**Dize** Düzenleyicisi sağlar zaten kullanımda bir kimliği kullanmayın. Bir kimliği kullanımda, zaten seçerseniz **dize** Düzenleyicisi bunu size bildirir ve ardından genel benzersiz kimliği örneğin Ata `IDS_STRING58113`.

#### <a name="to-add-a-string-table-entry"></a>Dize tablo girdisi eklemek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Dize tablosu içinde sağ tıklatın ve seçin **yeni dize** kısayol menüsünden.

1. İçinde **dize** Düzenleyicisi'ni seçin bir **kimliği** kimliği aşağı açılan listesinden veya türü kimliği ile doğrudan bir yerde.

1. Düzen **değer**, gerekirse.

1. İçin bir giriş türü **açıklamalı alt yazı**.

   > [!NOTE]
   > Null dizeler Windows dize tablolarında izin verilmez. Boş bir dize olan dize tablosunda bir giriş oluşturmak, "Lütfen gir bir dize Bu tablo girişi için" için soran bir ileti alırsınız.

#### <a name="to-delete-a-string-table-entry"></a>Dize tablosu girişi silmek için

Silmek istediğiniz girişini seçin. Ardından aşağıdakilerden birini yapın:

- Üzerinde **Düzenle** menüsünde **Sil**.

- Sağ tıklayın ve silmek istediğiniz dizeyi **Sil** kısayol menüsünden.

- Tuşuna **Sil** anahtarı.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Bir dizeyi bir kaynak betik dosyasını diğerine taşımak için

1. Dize tabloları içinde her iki .rc dosyası açın. (Daha fazla bilgi için [kaynaklar içinde bir kaynak betik dosyası dışında sonuna bir proje görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)

1. Sağ tıklayın, istediğiniz Taşı ve dize **Kes** kısayol menüsünden.

1. Hedef imleci **Dize Düzenleyicisi** penceresi.

1. Dize taşımak istediğiniz .rc dosyasına sağ tıklayın ve seçin **Yapıştır** kısayol menüsünden.

   > [!NOTE]
   > Varsa **kimliği** veya **değer** ile varolan taşınan dize çakışmalar **kimliği** veya **değer** hedef dosyasında ya da **Kimliği** veya **değer** taşınan dize değişiklikleri. Bir dize ile aynı varsa **kimliği**, **kimliği** taşınan dize değişiklikleri. Bir dize ile aynı varsa **değer**, **değer** taşınan dize değişiklikleri.

### <a name="to-change-the-properties-of-a-string-resource"></a>Bir dize kaynağının özelliklerini değiştirmek için

Yerinde düzenleme kimliği, değer ve açıklamalı alt yazı özelliklerini değiştirmek için kullanabilirsiniz.

#### <a name="to-change-a-string-or-its-identifier"></a>Bir dize veya tanımlayıcısını değiştirmek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Düzenle ve çift dize seçin **kimliği**, **değer**, veya **açıklamalı alt yazı** sütun. Artık şunları yapabilirsiniz:

   - Seçin bir **kimliği** gelen **kimliği açılan** liste veya türü bir `ID` doğrudan yerinde.

   - Farklı bir sayı yazın **değer** sütun.

   - Tür düzenlemeleri **açıklamalı alt yazı** sütun.

        > [!NOTE]
        >  Bir dizenin özelliklerini de düzenleyebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>Birden çok dize kaynakları resim yazısı özelliğini değiştirmek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Basılı tutarak değiştirmek istediğiniz dizeleri seçin **Ctrl** anahtar her birini seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), değiştirmek istediğiniz özelliği için yeni bir değer yazın.

1. Tuşuna **girin**.

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>Biçimlendirme veya özel karakterler için bir dize kaynağı eklemek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Değiştirmek istediğiniz dizeyi seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), herhangi bir standart kaçış dizileri aşağıda listelenen metinde ekleme **açıklamalı alt yazı** kutusu ve ENTER tuşuna **Enter**.

   |Bu alınacağı|Bunu yazın|
   |-----------------|---------------|
   | Yeni satır | \\N |
   | satır başı | \\r |
   | Tab | \\T |
   | Ters eğik çizgi (\\) | \\\\ |
   | ASCII karakteri | \\ddd (sekizlik gösterim) |
   | Uyarı (zil) | \\A |

> [!NOTE]
> **Dize** Düzenleyicisi kaçan ASCI karakter kümesini desteklemiyor. Yalnızca yukarıda listelenen kullanabilirsiniz.

> [!NOTE]
> Windows, boş dize tabloları oluşturulmasına izin vermiyor. Dize tablosu giriş yok oluşturursanız, kaynak dosyasını kaydettiğinizde, otomatik olarak silinir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Dizeler](https://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)<br/>
[Dizeleri hakkında](/windows/desktop/menurc/about-strings)<br/>
[Pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio)