---
description: 'Daha fazla bilgi edinin: Dize Düzenleyicisi (C++)'
title: Dize Düzenleyicisi (C++)
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
ms.openlocfilehash: 44f8d5b92b9eba805fda7607ce15230fc81748f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263289"
---
# <a name="string-editor-c"></a>Dize Düzenleyicisi (C++)

Dize tablosu, uygulamanızın tüm dizeleri için kimlikler, değerler ve açıklamalı alt yazı listesini içeren bir Windows kaynağıdır. Örneğin, durum çubuğu istemleri dize tablosunda bulunur.

Bir uygulama geliştirirken, her dil veya koşul için bir tane olmak üzere birkaç dize tablonuz olabilir. Ancak, yürütülebilir bir modülün yalnızca bir dize tablosu vardır. Tabloları farklı dll 'Lere yerleştirirseniz çalışan bir uygulama birkaç dize tablosuna başvurabilir.

Dize tabloları, uygulamanızı farklı dillere yerelleştirmek kolaylaştırır. Tüm dizeler bir dize tabloeyse, kaynak kodu değiştirmeden dizeleri (ve diğer kaynakları) çevirerek uygulamayı yerelleştirebilirsiniz. Bu durum, kaynak dosyalardaki çeşitli dizeleri el ile bulma ve değiştirme özelliğinden daha tercih edilir.

> [!NOTE]
> Windows boş dize tablolarının oluşturulmasına izin vermez. Girişi olmayan bir dize tablosu oluşturursanız, kaynak dosyasını kaydettiğinizde bu otomatik olarak silinir.

## <a name="how-to"></a>Nasıl yapılır

**Dize düzenleyici** şunları yapmanızı mümkün:

### <a name="to-find-a-string-resource-in-the-string-table"></a>Dize tablosunda bir dize kaynağı bulmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak dize tablosunu açın.

1. Menü **Düzenle**  >  **Bul ve Değiştir** ' e gidin ve **bul**' ı seçin.

1. **Aranan kutusunda,** açılan listeden önceki bir arama dizesini seçin veya bulmak istediğiniz dizenin başlık metnini veya kaynak tanımlayıcısını yazın.

1. **Bul** seçeneklerinden birini belirleyin ve **Sonrakini Bul**' u seçin.

> [!TIP]
> Dosyaları ararken [Normal ifadeleri](/visualstudio/ide/using-regular-expressions-in-visual-studio) kullanmak Için, **düzenleme** menüsündeki **dosyaları bul** komutunu kullanın.
>
> Bir Düzenle eşleştirmek için normal bir ifade yazın veya normal arama ifadelerinin listesini göstermek için **Aranan** kutusunun sağındaki düğmeyi seçin. Bu listeden bir ifade seçtiğinizde, **Aranan kutusunda arama** metni olarak değiştirilir.
>
> Normal ifadeler kullanırsanız, şunu **kullanın: normal ifadeler** onay kutusunun seçili olduğundan emin olun.

### <a name="to-add-or-delete-a-string-resource"></a>Bir dize kaynağı ekleme veya silme

Dize **düzenleyicisini** kullanarak String tablosuna hızlıca girdi ekleyebilir veya silebilirsiniz. Yeni dizeler tablonun sonuna yerleştirilir ve bir sonraki kullanılabilir tanımlayıcı verilir. [Özellikler penceresi](/visualstudio/ide/reference/properties-window) **kimliği**, **değeri** veya **açıklamalı alt yazı** özelliklerini gerektiği gibi düzenleyebilirsiniz.

**Dize Düzenleyicisi** , zaten kullanımda olan bir kimliği kullanmanıza olanak sağlar. Zaten kullanımda olan bir KIMLIĞI seçerseniz, **Dize Düzenleyicisi** sizi bilgilendirir ve örneğin bir genel benzersiz kimlik atar `IDS_STRING58113` .

#### <a name="to-add-a-string-table-entry"></a>Bir dize tablosu girdisi eklemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak dize tablosunu açın.

1. Dize tablosunun içine sağ tıklayın ve **Yeni dize**' yi seçin.

1. **Dize düzenleyicisinde**, **kimlik** aşağı açılan listesinden bir **kimlik** seçin veya doğrudan bir *kimlik* yazın.

1. Gerekirse **değeri** düzenleyin.

1. **Başlık** için bir giriş yazın.

   > [!NOTE]
   > Windows dize tablolarında null dizelere izin verilmez. Dize tablosunda boş bir dize olan bir girdi oluşturursanız, **Bu tablo girişi için bir dize girmenizi** isteyen bir ileti alırsınız.

#### <a name="to-delete-a-string-table-entry"></a>Bir dize tablosu girişini silmek için

Silmek istediğiniz girişi seçin ve aşağıdakilerden birini yapın:

- Menü **Düzenle**  >  **Sil**' e gidin.

- Silmek istediğiniz dizeye sağ tıklayın ve **Sil**' i seçin.

- **Delete** tuşuna basın.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Bir dizeyi bir kaynak betik dosyasından diğerine taşımak için

1. [Dize tablolarını. RC dosyalarında açın](../windows/how-to-create-a-resource-script-file.md).

1. Taşımak istediğiniz dizeye sağ tıklayın ve **Kes**' i seçin.

1. İmleci hedef **Dize Düzenleyicisi** penceresine yerleştirin.

1. Dizeyi taşımak istediğiniz *. RC* dosyasında sağ tıklayıp **Yapıştır**' ı seçin.

> [!NOTE]
> Taşınan dizenin **kimliği** veya **değeri** hedef dosyadaki mevcut bir **kimlik** veya **değerle** çakışırsa, bu **kimlik** ya da taşınan dizenin **değeri** değişir.

### <a name="to-change-the-properties-of-a-string-resource"></a>Bir dize kaynağının özelliklerini değiştirmek için

**Kimliği**, **değeri** ve **açıklamalı alt yazı** özelliklerini değiştirmek için yerinde Düzenle ' yi kullanabilirsiniz.

> [!NOTE]
> Ayrıca, [Özellikler penceresi](/visualstudio/ide/reference/properties-window)bir dizenin özelliklerini düzenleyebilirsiniz.

#### <a name="to-change-a-string-or-its-identifier"></a>Bir dizeyi veya tanımlayıcısını değiştirmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak dize tablosunu açın.

1. Düzenlemek istediğiniz dizeyi seçin ve **kimliği**, **değeri** veya **açıklamalı alt yazı** sütununu çift tıklatın, ardından şunları yapabilirsiniz:

   - **Kimlik** açılan listesinden bir **kimlik** seçin veya doğrudan bir *kimlik* yazın.

   - **Değer** sütununa farklı bir sayı yazın.

   - **Açıklamalı alt yazı** sütununda düzenleme yazın.

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>Birden çok dize kaynağı başlık özelliğini değiştirmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak dize tablosunu açın.

1. Her birini seçerken **CTRL** tuşunu basılı tutarak değiştirmek istediğiniz dizeleri seçin.

1. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window)değiştirmek istediğiniz özellik için yeni bir değer yazın.

1.  **Enter** tuşuna basın.

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>Bir dize kaynağına biçimlendirme veya özel karakterler eklemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak dize tablosunu açın.

1. Değiştirmek istediğiniz dizeyi seçin.

1. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), aşağıda listelenen standart kaçış sıralarını **başlık** kutusundaki metne ekleyin ve **ENTER** tuşuna basın.

   |Bunu almak için...|Şunu yazın...|
   |-----------------|---------------|
   | Yeni satır | \\No |
   | Satır başı | \\sağ |
   | Tab | \\şı |
   | Ters eğik çizgi ( \\ ) | \\\\ |
   | ASCII karakteri | \\ddd (sekizlik Gösterim) |
   | Uyarı (zil) | \\a |

   > [!NOTE]
   > **Dize Düzenleyicisi** , kaçan Yoki karakterlerinin tam kümesini desteklemez. Yalnızca yukarıda listelenen olanları kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak düzenleyicileri](../windows/resource-editors.md) 
 [Dizeler](/windows/win32/menurc/strings)<br/>
[Dizeler hakkında](/windows/win32/menurc/about-strings)<br/>
[Pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio)
