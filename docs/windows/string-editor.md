---
title: String Düzenleyicisi (C++)
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
ms.openlocfilehash: b0fb077752cf1912e07175c68cdc8acfe758b0c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370233"
---
# <a name="string-editor-c"></a>String Düzenleyicisi (C++)

Dize tablosu, uygulamanızın tüm dizeleri için bir sözcük, değer ve altyazılistesi içeren bir Windows kaynağıdır. Örneğin, durum çubuğu istemleri dize tablosunda yer alır.

Bir uygulama geliştirirken, her dil veya koşul için bir tane olmak üzere birkaç dize tablonuz olabilir. Ancak, çalıştırılabilir bir modülün yalnızca bir dize tablosu vardır. Tabloları farklı DL'lere koyarsanız, çalışan bir uygulama birkaç dize tabloya başvurulabilir.

String tablolar, uygulamanızı farklı dillerde yerelleştirmeyi kolaylaştırır. Tüm dizeleri bir dize tablosunda ise, kaynak kodu değiştirmeden dizeleri (ve diğer kaynakları) çevirerek uygulamayı yerelleştirebilirsiniz. Bu durum, kaynak dosyalardaki çeşitli dizeleri el ile bulmak ve değiştirmekten daha fazla arzu edilir.

> [!NOTE]
> Windows boş dize tabloları oluşturulmasına izin vermez. Girişsiz bir dize tablosu oluşturursanız, kaynak dosyasını kaydettiğinizde otomatik olarak silinir.

## <a name="how-to"></a>Nasıl yapılır

**String Düzenleyicisi** şunları yapmanızı sağlar:

### <a name="to-find-a-string-resource-in-the-string-table"></a>Dize tablosunda bir dize kaynağı bulmak için

1. [Kaynak Görünümü'ndeki](how-to-create-a-resource-script-file.md#create-resources)simgesini çift tıklatarak dize tablosunu açın.

1. **Bul** > **ve Değiştir** menüsüne gidin ve **Bul'u**seçin.

1. **Ne** Bul kutusunda, açılan listeden önceki bir arama dizesini seçin veya bulmak istediğiniz dizenin resim yazısı metnini veya kaynak tanımlayıcısını yazın.

1. **Seçeneklerden** birini seçin ve **İleri'yi Bul'u**seçin.

> [!TIP]
> Dosyaları ararken [normal ifadeleri](/visualstudio/ide/using-regular-expressions-in-visual-studio) kullanmak için **Düzenle** menüsündeki **Dosyalarda Bul** komutunu kullanın.
>
> Bir deseni eşleştirmek için normal bir ifade yazın veya normal arama ifadelerinin listesini görüntülemek için **Bul** kutusunun sağındaki düğmeyi seçin. Bu listeden bir ifade seçtiğinizde, bu ifade **ne** bul kutusundaki arama metni olarak ikame edilir.
>
> Normal ifadeler kullanıyorsanız, **Kullanım: Normal İfadeler** onay kutusunun seçildiğinden emin olun.

### <a name="to-add-or-delete-a-string-resource"></a>Dize kaynağı eklemek veya silmek için

**String**Düzenleyicisi'ni kullanarak string tablosuna girişleri hızla ekleyebilir veya silebilirsiniz. Yeni dizeleri tablonun sonuna yerleştirilir ve bir sonraki kullanılabilir tanımlayıcı verilir. Gerektiğinde [Özellikler penceresindeki](/visualstudio/ide/reference/properties-window) **kimlik,** **Değer**veya **Resim Yazısı** özelliklerini atabilirsiniz.

**String** Düzenleyicisi, zaten kullanılmakta olan bir kimliği kullanmadığınızdan emin olmasını sağlar. Zaten kullanılmakta olan bir kimlik seçerseniz, **String Düzenleyicisi** sizi bilgilendirecek `IDS_STRING58113`ve ardından genel bir benzersiz kimlik atayacaktır, örneğin.

#### <a name="to-add-a-string-table-entry"></a>Dize tablo girişi eklemek için

1. [Kaynak Görünümü'ndeki](how-to-create-a-resource-script-file.md#create-resources)simgesini çift tıklatarak dize tablosunu açın.

1. Dize tablosu nun içine sağ tıklayın ve **Yeni Dize'yi**seçin.

1. String **Düzenleyicisi'nde,** **kimlik** açılır listesinden bir **kimlik** seçin veya doğrudan yerine bir *kimlik* yazın.

1. **Gerekirse Değeri**edin.

1. **Resim Yazısı**için bir giriş yazın.

   > [!NOTE]
   > Windows dize tablolarında null dizeleri izin verilmez. Dize tablosunda null dize olan bir giriş oluşturursanız, bu tablo **girişi için lütfen bir dize girmenizi**isteyen bir ileti alırsınız.

#### <a name="to-delete-a-string-table-entry"></a>Dize tablo girişini silmek için

Silmek istediğiniz girişi seçin ve aşağıdakilerden birini yapın:

- Menüye git**Sil** **düzenle** > .

- Silmek için dize sağ tıklatın ve **Sil**seçin.

- **Sil** tuşuna basın.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Bir dizeyi bir kaynak komut dosyası dosyasından diğerine taşımak için

1. [Her iki .rc dosyasındaki dize tablolarını açın.](../windows/how-to-create-a-resource-script-file.md)

1. Hareket etmek için dize sağ tıklatın ve **Kes**seçin.

1. İmleci hedef String **Düzenleyicipenceresine** yerleştirin.

1. Dizeyi taşımak istediğiniz *.rc* dosyasında, sağ tıklatın ve **Yapıştır'ı**seçin.

> [!NOTE]
> Taşınan **dize** kimliği veya **Değeri,** geçerli bir **kimlikle** veya hedef dosyadaki **değerle** çakışMaya çıkarsa, bu **kimlik** veya taşınan **dize** değeri değişir.

### <a name="to-change-the-properties-of-a-string-resource"></a>Dize kaynağının özelliklerini değiştirmek için

**Kimlik,** **Değer**ve **Resim Yazısı** özelliklerini değiştirmek için yerinde düzenlemeyi kullanabilirsiniz.

> [!NOTE]
> Ayrıca [Özellikler penceresinde](/visualstudio/ide/reference/properties-window)bir dize özelliklerini de edebilirsiniz.

#### <a name="to-change-a-string-or-its-identifier"></a>Bir dizeyi veya tanımlayıcısını değiştirmek için

1. [Kaynak Görünümü'ndeki](how-to-create-a-resource-script-file.md#create-resources)simgesini çift tıklatarak dize tablosunu açın.

1. Görüntülemek istediğiniz dizeyi seçin ve **Kimlik,** **Değer**veya **Resim Yazısı** sütununa çift tıklayın, ardından şunları yapabilirsiniz:

   - **Kimlik** açılır listesinden bir **kimlik** seçin veya doğrudan yerine bir *kimlik* yazın.

   - **Değer** sütununa farklı bir sayı yazın.

   - **Resim Yazısı** sütununa yapılan ları yazın.

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>Birden çok dize kaynağının resim yazısı özelliğini değiştirmek için

1. [Kaynak Görünümü'ndeki](how-to-create-a-resource-script-file.md#create-resources)simgesini çift tıklatarak dize tablosunu açın.

1. Her birini seçerken **Ctrl** tuşunu basılı tutarak değiştirmek istediğiniz dizeleri seçin.

1. Özellikler [Penceresinde,](/visualstudio/ide/reference/properties-window)değiştirmek istediğiniz özellik için yeni bir değer yazın.

1. **Enter**'a basın.

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>Dize kaynağına biçimlendirme veya özel karakterler eklemek için

1. [Kaynak Görünümü'ndeki](how-to-create-a-resource-script-file.md#create-resources)simgesini çift tıklatarak dize tablosunu açın.

1. Değiştirmek istediğiniz dizeyi seçin.

1. Özellikler [Penceresinde,](/visualstudio/ide/reference/properties-window) **Resim Yazısı** kutusundaki metne aşağıda listelenen standart kaçış dizilerinden herhangi birini ekleyin ve **Enter**tuşuna basın.

   |Bu almak için ...|Bunu yazın...|
   |-----------------|---------------|
   | Yeni satır | \\n |
   | Satır başı | \\R |
   | Tab | \\T |
   | Ters eğik çizgi (\\) | \\\\ |
   | ASCII karakteri | \\ddd (sekizli gösterim) |
   | Uyarı (çan) | \\A |

   > [!NOTE]
   > **String** Düzenleyicisi, kaçan ASCI karakterlerinin tam kümesini desteklemez. Yalnızca yukarıda listelenenleri kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Editörleri](../windows/resource-editors.md)
[Dizeleri](/windows/win32/menurc/strings)<br/>
[Dizeleri Hakkında](/windows/win32/menurc/about-strings)<br/>
[Pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio)
