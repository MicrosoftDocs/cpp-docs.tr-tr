---
title: 'Nasıl yapılır: denetim erişimini ve değerlerini tanımlama (C++)'
ms.date: 02/15/2019
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls [C++], mnemonics
- access keys [C++], checking
- mnemonics [C++], checking for duplicate
- mnemonics
- mnemonics [C++], dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
- combo boxes [C++], Data property
- controls [C++], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- Data property
- combo boxes [C++], testing values
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
ms.openlocfilehash: 59d81c0b835171132ebf29739a4e130191a87769
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504459"
---
# <a name="how-to-define-control-access-and-values-c"></a>Nasıl yapılır: denetim erişimini ve değerlerini tanımlama (C++)

## <a name="tab-order"></a>Sekme sırası

Sekme sırası, **sekme** tuşunun giriş odağını bir denetimden bir iletişim kutusu içindeki bir sonrakine taşıdıkları sıradır. Genellikle sekme sırası, iletişim kutusunda soldan sağa ve yukarıdan aşağıya doğru ilerler. Her denetim, bir denetimin giriş odağını alıp almayacağını belirleyen bir **TabStop** özelliğine sahiptir.

- Bir denetimin giriş odağını ayarlamak için, [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), **TabStop** özelliğinde **true** veya **false** ' ı seçin.

**TabStop** özelliği **true** olarak ayarlanmış olmayan denetimlerin, özellikle açıklamalı alt yazı olmayan denetimlerde sekme sırasının bir parçası olması gerekir. İlgili denetim için bir erişim anahtarı içeren statik metin, sekme düzeninde ilgili denetimin hemen önüne gelmelidir.

> [!NOTE]
> İletişim kutusu çakışan denetimler içeriyorsa, sekme sırasını değiştirmek denetimlerin görüntülenme şeklini değiştirebilir. Sekme sırasının ilerleyen kısımlarında yer alan denetimler her zaman, sekme düzeninde önce gelen örtüşen denetimlerin en üstünde görüntülenir.

- Tüm denetimlerin geçerli sekme sırasını görüntülemek için menü **biçimi**  >  **sekme sırası**' na gidin veya **CTRL**  +  **D**tuşuna basın.

   Her denetimin sol üst köşesindeki bir sayı geçerli sekme düzeninde yerini gösterir.

- Tüm denetimlerin sekme sırasını değiştirmek için, menü **biçimi**  >  **sekme sırası** ' na gidin ve **sekme** tuşunu izlemek istediğiniz sırada her bir denetimi seçerek sekme sırasını ayarlayın.

- İki veya daha fazla denetimin sekme sırasını değiştirmek için menü **biçimi**  >  **sekme sırası**' na gidin. **CTRL** tuşunu basılı tutun ve sırasıyla değişikliğin başlayacağı denetimi seçin ve ardından **CTRL** tuşunu bırakın ve **sekme** tuşunun bu noktadan izlemesini istediğiniz sırada denetimleri seçin.

   Örneğin, denetimlerin sırasını değiştirmek istiyorsanız, `7` `9` **CTRL**tuşunu basılı tutun, ardından önce denetim ' i seçin `6` .

- Belirli bir denetimi sayı olarak ayarlamak `1` veya sekme düzeninde ilk olarak denetlemek için denetime çift tıklayın.

> [!TIP]
> **Sekme** sırası moduna girdikten sonra **sekme sırası** modundan çıkmak için **ESC** veya **ENTER** tuşuna basın ve sekme sırasını değiştirme özelliğini devre dışı bırakın.

## <a name="mnemonics-access-keys"></a>Anımsatıcıları (erişim tuşları)

Normal olarak, klavye kullanıcıları giriş odağını **sekme** ve **ok** tuşlarıyla iletişim kutusunda bir denetimden diğerine taşır. Ancak, kullanıcıların tek bir tuşa basarak bir denetim seçmesini sağlayan bir erişim anahtarı (bir anımsatıcı veya kolay hatırlama adı) tanımlayabilirsiniz.

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Görünür bir açıklamalı alt yazı (basma düğmeleri, onay kutuları ve radyo düğmeleri) ile bir denetim için erişim anahtarı tanımlama

1. İletişim kutusunda denetimi seçin.

1. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), **başlık** özelliğinde, denetim için yeni bir ad yazın ve `&` Bu denetimin erişim anahtarı olarak istediğiniz harfin önüne bir ve işareti () koyun. Örneğin, `&Radio1`.

1.  **Enter** tuşuna basın.

   Görüntülenen başlıkta, Access tuşunu göstermek için bir alt çizgi görünür, örneğin, **R**adio1.

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Görünür açıklamalı alt yazı olmadan bir denetim için erişim anahtarı tanımlama

1. [Araç kutusunda](/visualstudio/ide/reference/toolbox) **statik metin** denetimi kullanarak denetim için bir başlık oluşturun.

1. Statik metin başlığı içinde, `&` erişim anahtarı olarak istediğiniz harfin önüne bir ampersan () yazın.

1. Statik metin denetiminin, sekme düzeninde denetim etiketlerinin hemen önünde bulunduğundan emin olun.

> [!NOTE]
> İletişim kutusu içindeki tüm erişim tuşları benzersiz olmalıdır. Yinelenen erişim anahtarlarını denetlemek için menü **biçimi**  >  **Denetim anımsatıcıları**' na gidin.

## <a name="combo-box-values"></a>Birleşik giriş kutusu değerleri

**İletişim kutusu Düzenleyicisi** açık olduğu sürece bir açılan kutu denetimine değerler ekleyebilirsiniz.

> [!TIP]
> **İletişim kutusu düzenleyicideki**kutuyu *boyutlandırmadan önce* tüm değerleri açılan kutuya eklemek iyi bir fikirdir veya Birleşik denetimde görünmesi gereken metni kesmeyebilirsiniz.

### <a name="to-enter-values-into-a-combo-box-control"></a>Birleşik giriş kutusu denetimine değer girmek için

1. Seçerek Birleşik giriş kutusu denetimini seçin.

1. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), **veri** özelliğine aşağı kaydırın.

   > [!NOTE]
   > Özellikleri türe göre gruplandırılmış olarak görüntülüyorsanız, **veriler** **çeşitli** özelliklerde görüntülenir.

1. **Veri** özelliği için değer alanını seçin ve veri değerlerinizi noktalı virgülle ayırarak yazın.

   > [!NOTE]
   > Boşluklar, aşağı açılan listede alta doğru sıralama yaptığından, değerler arasına boşluk yerleştirmeyin.

1. Değer ekleme işiniz bittiğinde **ENTER** tuşuna basın.

Birleşik giriş kutusunun aşağı açılan kısmını büyütme hakkında daha fazla bilgi için bkz. [Birleşik giriş kutusunun boyutunu ve açılan listesini ayarlama](./arrangement-of-controls-on-dialog-boxes.md).

> [!NOTE]
> Bu yordamı kullanarak Win32 projelerine değer ekleyemezsiniz ( **Data** özelliği Win32 projeleri için gridir). Win32 projelerinin bu özelliği ekleyen kitaplıkları olmadığından, programlı bir şekilde Win32 projesi içeren bir Birleşik giriş kutusuna değer eklemeniz gerekir.

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>Birleşik giriş kutusundaki değerlerin görünümünü test etmek için

1. **Data** özelliğine değer girdikten sonra [Iletişim kutusu Düzenleyicisi araç çubuğundaki](./dialog-editor.md) **Test** düğmesini seçin.

1. Tüm değer listesini kaydırmayı deneyin. Değerler, **Özellikler** penceresinde **veri** özelliğinde yazıldığı şekilde tam olarak görünür. Yazım veya büyük harf denetimi yoktur.

1. **İletişim kutusu** düzenleyicisine geri dönmek için **ESC** tuşuna basın.

## <a name="radio-button-values"></a>Radyo düğmesi değerleri

Bir iletişim kutusuna radyo düğmeleri eklediğinizde, gruptaki ilk düğmenin **Özellikler** penceresinde bir **Grup** özelliği ayarlayarak onları bir grup olarak değerlendirin. Bu radyo düğmesinin denetim KIMLIĞI, ardından [üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard)'nda görünür ve radyo düğmeleri grubu için bir üye değişkeni eklemenize olanak tanır.

İletişim kutusunda birden fazla radyo düğmesi grubuna sahip olabilirsiniz. Aşağıdaki yordamı kullanarak her grubu ekleyin.

### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>Bir iletişim kutusuna radyo düğmesi grubu eklemek için

1. [Araç kutusu penceresinde](/visualstudio/ide/reference/toolbox) radyo düğmesi denetimini seçin ve denetimin yerleştirileceği yeri iletişim kutusunda seçin.

1. İhtiyaç duyduğunuz kadar çok sayıda radyo düğmesi eklemek için yukarıdaki adımı yineleyin. Gruptaki radyo düğmelerinin sekme düzeninde ardışık olduğundan emin olun.

1. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), sekme sırasındaki *Ilk* radyo düğmesinin **Grup** özelliğini **doğru**olarak ayarlayın.

   **Group** özelliğini **true** olarak değiştirmek, kaynak betiğin iletişim nesnesindeki düğme girdisine ws_group stilini ekler ve kullanıcının düğme grubunda bir seferde birden fazla radyo düğmesi seçmesini önler (Kullanıcı bir radyo düğmesini seçerse, gruptaki diğerleri temizlenir).

   > [!NOTE]
   > Yalnızca gruptaki ilk radyo düğmesinin **Group** özelliği **true**olarak ayarlanmalıdır. Düğme grubunun parçası olmayan ek denetimleriniz varsa, *grubun dışındaki* Ilk denetimin **Grup** özelliğini de **true** olarak ayarlayın. **Ctrl** + Sekme sırasını görüntülemek için CTRL**D** 'yi kullanarak ilk denetimi grup dışında hızlıca belirleyebilirsiniz.

### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>Radyo düğmesi grubuna üye değişkeni eklemek için

1. Sekme düzeninde (baskın denetim ve **Group** özelliği **true**olarak ayarlanan) ilk radyo düğmesi denetimine sağ tıklayın ve **değişken Ekle**' yi seçin.

1. [Üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard)'Nda, **denetim değişkeni** onay kutusunu seçin, sonra **da radyo düğmesini** seçin.

   - **Değişken adı** kutusuna yeni üye değişkeni için bir ad yazın.

   - **Değişken türü** liste kutusunda int ' i seçin **`int`** veya yazın *int*.

   Şimdi, hangi radyo düğmesinin seçili görünmesi gerektiğini belirtmek için kodunuzu değiştirebilirsiniz. Örneğin, `m_radioBox1 = 0;` gruptaki ilk radyo düğmesini seçer.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Iletişim kutusu denetimlerini Yönet](controls-in-dialog-boxes.md)<br/>
[Nasıl yapılır: denetimleri ekleme, düzenleme veya silme](adding-editing-or-deleting-controls.md)<br/>
[Nasıl yapılır: düzen denetimleri](arrangement-of-controls-on-dialog-boxes.md)<br/>
