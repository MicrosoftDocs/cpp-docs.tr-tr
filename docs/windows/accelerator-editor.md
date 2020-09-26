---
title: Hızlandırıcı Düzenleyici (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.accelerator.F1
- vc.editors.accelerator
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
- VIRTKEY
- Key property
- ID property
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
- searching, in accelarator tables
- accelerator tables [C++], finding entries
- accelerator tables [C++], adding entries
- New Accelerator command
- accelerator tables [C++], deleting entries
- keyboard shortcuts [C++], deleting entry from accelerator table
- accelerator tables [C++], copying entries
- rc files [C++], moving an accelerator table entry
- .rc files [C++], moving accelerator table entries
- accelerator tables [C++], moving entries
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: c98ff1fd44b73b3f204e9b952836c387f7f21146
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91353096"
---
# <a name="accelerator-editor-c"></a>Hızlandırıcı Düzenleyici (C++)

Hızlandırıcı tablosu, kısayol tuşları olarak bilinen Hızlandırıcı tuşlarının listesini ve bunlarla ilişkili komut tanımlayıcılarını içeren bir C++ Windows kaynağıdır. Programda birden fazla Hızlandırıcı tablosu olabilir.

Genellikle Hızlandırıcılar, bir menü veya araç çubuğunda de bulunan program komutları için klavye kısayolları olarak kullanılır. Ancak, kısayol tablosu ile ilişkili bir kullanıcı arabirimi nesnesine sahip olmayan komutlara ilişkin anahtar birleşimlerini tanımlamak için Hızlandırıcı tablosunu kullanabilirsiniz.

> [!TIP]
> **Hızlandırıcı düzenleyicisini**kullanırken, sık kullanılan komutların kısayol menüsünü göstermek için sağ tıklayın. Kullanılabilir komutlar, işaretçinin işaret ettiği işe bağlıdır.

[Sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) kullanarak kısayol tuşu komutlarını koda bağlayabilirsiniz. Önceden tanımlanmış Hızlandırıcı tuşlarının bir listesi için bkz. [hızlandırıcı tuşları](predefined-accelerator-keys.md).

> [!NOTE]
> Windows boş Hızlandırıcı tabloları oluşturmanıza izin vermez. Girişi olmayan bir Hızlandırıcı tablosu oluşturursanız, tabloyu kaydettiğinizde bu otomatik olarak silinir.

## <a name="accelerator-properties"></a>Hızlandırıcı özellikleri

[Özellikler penceresi](/visualstudio/ide/reference/properties-window) Hızlandırıcı özelliklerini dilediğiniz zaman ayarlayabilirsiniz. Hızlandırıcı tablosundaki Hızlandırıcı özelliklerini değiştirmek için **Hızlandırıcı düzenleyicisini** de kullanabilirsiniz. **Özellikler** penceresi veya **Hızlandırıcı Düzenleyicisi** kullanılarak yapılan değişiklikler aynı sonuca sahiptir; düzenlemeler hemen Hızlandırıcı tablosuna yansıtılır.

**ID** özelliği Program kodundaki her bir Hızlandırıcı tablosu girişine başvurur. Bu giriş, bir Kullanıcı Hızlandırıcı tuşuna veya bir tuş birleşimine bastığında programın aldığı komut değeridir. Hızlandırıcının bir menü öğesiyle aynı olmasını sağlamak için, bu **kimliği** aynı yapın, böylece Hızlandırıcı tablosunun **kimliği** , menü kaynağının **kimliğiyle** aynı olur.

Her hızlandırıcı **kimliği** üç özelliğe sahiptir: **değiştirici**, **anahtar**ve **tür**

**Değiştirici** özelliği hızlandırıcı için denetim tuş bileşimlerini ayarlar.

> [!NOTE]
> **Özellikler** penceresinde, **değiştirici** özelliği, hepsi bağımsız olarak denetlenebilen üç ayrı **Boole** özelliği olarak görünür: **alt**, **CTRL**ve **Shift**.

Hızlandırıcı tablosundaki **değiştirici** özelliğinin geçerli girişleri şunlardır:

   |Değer|Açıklama|
   |-----------|-----------------|
   |**Hiçbiri**|Kullanıcı yalnızca **anahtar** değerine basar.<br/><br/>Bu değer, 026 aracılığıyla (**CTRL + a** ile **CTRL + Z**arasında) YORUMLANAN bir ASCII/ANSI değerleriyle en etkili şekilde kullanılır.|
   |**Alternatif**|Kullanıcı, **anahtar** değerinden önce **alt** tuşuna basmanız gerekir.|
   |**T**|Kullanıcının **anahtar** değerinden önce **CTRL** tuşuna BASMASı gerekir, ASCII türünde geçerli değildir.|
   |**Shift**|Kullanıcı, **anahtar** değerinden önce **SHIFT** tuşuna basmalıdır.|
   |**Ctrl + alt**|Kullanıcı, **anahtar** değerinden önce **CTRL** ve **alt** tuşlarına basarak ASCII türüyle geçerli değildir.|
   |**Ctrl + Shift**|Kullanıcı, **anahtar** değerinden önce **CTRL** ve **SHIFT** tuşlarına basarak ASCII türüyle geçerli değildir.|
   |**Alt + SHIFT**|Kullanıcı, **anahtar** değerinden önce **alt** ve **SHIFT** tuşlarına basarak ASCII türüyle geçerli değildir.|
   |**CTRL + ALT + SHIFT**|Kullanıcı, **anahtar** değerinden önce **CTRL**, **alt**ve **SHIFT** tuşlarına basarak ASCII türüyle geçerli değildir.|

**Anahtar** özelliği, hızlandırıcı olarak kullanılacak gerçek anahtarı ayarlar.

Aşağıda Hızlandırıcı tablosundaki **anahtar** özelliği için geçerli girişler verilmiştir:

   |Değer|Açıklama|
   |-----------|-----------------|
   |Ondalık biçimdeki 0 ile 255 arasında bir tamsayı.|Değer, değerin ASCII veya ANSI olarak değerlendirilip değerlendirilmediğini aşağıdaki gibi belirler:<br/><br/>   -Tek basamaklı sayılar, ASCII veya ANSI değerleri yerine her zaman karşılık gelen anahtar olarak yorumlanır.<br/>   -1 ile 26 arasındaki değerler, önüne sıfır ile basıldığında, **CTRL** tuşu basılı tutulduğunda alfabedeki harflerin ASCII değerini temsil eden ^ a-^ Z olarak yorumlanır.<br/>   -27-32 değeri her zaman 027 ile 032 arasındaki üç basamaklı ondalık değerler olarak yorumlanır.<br/>   -033 ile 255 arasındaki değerler, önünde 0 ' ın, ANSI değerleri olarak yorumlanıp yorumlanmayacağı.|
   |Tek bir klavye karakteri.|Büyük harf A-Z veya 0-9 sayıları ASCII ya da sanal anahtar değerleri olabilir. Diğer tüm karakterler yalnızca ASCII 'dir.|
   |A-Z aralığındaki tek bir klavye karakteri (yalnızca büyük harf), önünde bir şapka (^), örneğin, ^ C.|Bu seçenek, **CTRL** tuşu basılı tutulduğunda, anahtarın ASCII değerini girer.|
   |Herhangi bir geçerli sanal anahtar tanımlayıcısı.|Hızlandırıcı tablosundaki açılan **anahtar** kutusu standart sanal anahtar tanımlayıcılarının bir listesini içerir.|

> [!NOTE]
> Bir ASCII değeri girerken, **değiştirici** özelliği seçenekleri sınırlıdır. Kullanılabilecek tek denetim anahtarı **alt** anahtardır.

> [!TIP]
> Hızlandırıcı tuşu tanımlayan bir kısayol, Hızlandırıcı tablosunda bir girişe veya birden çok girişe sağ tıklayıp, ardından **yazılan sonraki anahtar** ' ı seçip klavyede herhangi bir tuşa veya tuş kombinasyonlarına tıklamalıdır.
>
> Bu **sonraki anahtar yazılı** komut, **düzenleme** menüsünde de kullanılabilir.

**Type** özelliği, hızlandırıcı **kimliğiyle** ilişkili KıSAYOL tuşu BILEŞIMININ bir ASCII/ANSI anahtar değeri veya bir sanal anahtar (virtkey) birleşimi olarak yorumlanıp yorumlanmadığını belirler.

- **Tür** özelliği **ASCII**ise, **değiştirici** özelliği yalnızca veya olabilir `None` ya da `Alt` **CTRL** tuşunu kullanan bir hızlandırıcıya sahip olan anahtar önünde ile belirtilen bir hızlandırıcıya sahip olabilir `^` .

- **Tür** özelliği **Virtkey**Ise, **değiştirici** ve **anahtar** değerlerinin herhangi bir birleşimi geçerlidir.

> [!NOTE]
> Hızlandırıcı tablosuna bir değer girmek ve değeri ASCII/ANSI olarak kabul etmek istiyorsanız, tablodaki girdinin **türünü** seçin ve açılan listeden **ASCII** ' yi seçin. Ancak, **anahtarı**belirtmek için **düzenleme** menüsünden bir **sonraki anahtar yazılı** komutunu kullanırsanız, **anahtar** kodu girmeden *önce* , **Type** özelliğini **virtkey** iken **ASCII** olarak değiştirmeniz gerekir.

## <a name="accelerator-tables"></a>Hızlandırıcı tabloları

Bir C++ projesinde Hızlandırıcı Düzenleyicisi ' ni doğrudan **Hızlandırıcı düzenleyicisinde**yerinde düzenleme ile düzenleyebilirsiniz.

Aşağıdaki yordamlar standart özellik sayfalarının kullanımına başvurur, ancak hem yerinde düzenlenen hem de özellik sayfası yöntemi aynı sonuca sahiptir. Özellik sayfaları kullanılarak yapılan değişiklikler veya yerinde düzenlemenin kullanılması hemen Hızlandırıcı tablosuna yansıtılır.

### <a name="to-edit-in-an-accelerator-table"></a>Hızlandırıcı tablosunda düzenlemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak Hızlandırıcı tablosunu açın.

1. Tablodaki bir girişi seçin ve yerinde düzenlemeden etkinleştirmeyi seçin.

1. Açılan açılan kutudan seçim yapın veya değişiklik yapmak için yerinde yazın:

   - **Kimlik**için listeden seçin veya düzenlemek için yazın.

   - **Değiştirici**için listeden seçin.

   - **Anahtar**için listeden seçin veya düzenlemek için yazın.

   - **Tür**Için listeden **ASCII** veya **virtkey** ' i seçin.

### <a name="to-find-an-entry-in-an-open-accelerator-table"></a>Açık bir Hızlandırıcı tablosunda giriş bulmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak Hızlandırıcı tablosunu açın.

1. Sütunun içeriğini alfabetik olarak sıralamak için bir sütun başlığı seçin. Örneğin, Hızlandırıcı tablonuzdaki tüm kimlikleri alfabetik olarak göstermek için **kimlik** ' i seçin.

   Daha sonra listeyi tarayabilir ve girişi bulabilirsiniz.

### <a name="to-add-an-entry-to-an-accelerator-table"></a>Hızlandırıcı tablosuna giriş eklemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak Hızlandırıcı tablosunu açın.

1. Hızlandırıcı tablosuna sağ tıklayın ve **Yeni Hızlandırıcı**' yı seçin ya da tablonun en altındaki boş satır girişini seçin.

1. **Kimlik** kutusundaki aşağı açılan listeden bir **kimlik** seçin veya **kimlik** kutusuna yeni bir *kimlik* yazın.

1. Hızlandırıcı olarak kullanmak istediğiniz *anahtarı* yazın veya bir tuş bileşimini ayarlamak için sağ tıklayın ve yazılı bir **sonraki** anahtar ' ı seçin **Edit**  >  **Next Key Typed**.

1. Gerekirse **değiştiriciyi** değiştirin ve **yazın**ve **ENTER**tuşuna basın.

> [!NOTE]
> Tanımladığınız tüm Hızlandırıcıların benzersiz olduğundan emin olun. Aynı kimliğe herhangi bir etkisi olmadan atanmış birkaç anahtar birleşimine sahip olabilirsiniz, örneğin, **CTRL** + **P** ve **F8** her ikisi de ID_PRINT atanabilir. Ancak, birden fazla kimliğe atanmış anahtar birleşimine sahip olmak iyi çalışmaz, örneğin, **Ctrl** + hem ID_SPELL_CHECK hem de ID_THESAURUS için CTRL**Z** atanır.

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>Hızlandırıcı tablosundan bir girişi silmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak Hızlandırıcı tablosunu açın.

1. Silmek istediğiniz girişi seçin veya birden çok girdiyi seçmek için seçerken **CTRL** veya **SHIFT** tuşunu basılı tutun.

1. Sağ tıklayın ve **Sil**' i seçin veya menü **Düzenle**  >  **Sil**' e gidin.

> [!TIP]
> Silmek için **Delete** tuşuna da basabilirsiniz.

### <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>Bir Hızlandırıcı tablosu girişini başka bir kaynak betik dosyasına taşımak veya kopyalamak için

1. Hızlandırıcı tablolarını her iki kaynak betiği dosyasında da açın ve taşımak istediğiniz girişi seçin.

1. **Düzenle** menüsünde **Kopyala** veya **Kes**' i seçin.

1. Hedef kaynak betiği dosyasında bir giriş seçin ve **Düzenle** menüsünden **Yapıştır**' ı seçin.

> [!NOTE]
> Ayrıca, kopyalamak ve yapıştırmak için kısayol tuşlarını kullanabilirsiniz.

### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Çoklu Hızlandırıcı tuşlarının özelliklerini değiştirmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de simgesine çift tıklayarak Hızlandırıcı tablosunu açın.

1. Her birini seçerken **CTRL** tuşunu basılı tutarak değiştirmek istediğiniz Hızlandırıcı tuşlarını seçin.

1. [Özellikler penceresi](/visualstudio/ide/reference/properties-window) gidin ve tüm seçili Hızlandırıcıların paylaşmasını istediğiniz değerleri yazın.

> [!NOTE]
> Her değiştirici değeri, **Özellikler** penceresinde bir Boole özelliği olarak görünür. **Özellikler** penceresinde bir değiştirici değeri değiştirirseniz, Hızlandırıcı tablosu, yeni değiştiriciye daha önce orada olan değiştiricilere ek olarak davranır. Bu nedenle, herhangi bir değiştirici değeri ayarlarsanız, her hızlandırıcının aynı **değiştirici** ayarlarını paydığından emin olmak için bunların tümünü ayarlamanız gerekir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak düzenleyicileri](resource-editors.md)<br/>
[Hızlandırıcı tuşları](predefined-accelerator-keys.md)<br/>
