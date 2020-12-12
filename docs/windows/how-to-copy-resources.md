---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: kaynakları yönetme (C++)'
title: 'Nasıl yapılır: kaynakları yönetme (C++)'
ms.date: 02/14/2019
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
- vc.resvw.resource.changing
- vb.xmldesigner.data
- vs.resvw.resource.importing
- vc.resvw.resource.importing
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
- Language property [C++]
- .resx files [C++], editing
- resource files [C++], editing
- resx files [C++], editing
- resources [C++], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [C++], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 3720cb5f3ab3b99ecba798abce1e4fdba25f8646
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329390"
---
# <a name="how-to-manage-resources-c"></a>Nasıl yapılır: kaynakları yönetme (C++)

## <a name="copy-and-edit-resources"></a>Kaynakları kopyalama ve düzenleme

Kaynakları değiştirmeden bir dosyadan diğerine kopyalayabilir veya bir kaynağı kopyalarken bir kaynağın dilini veya koşulunu değiştirmenize olanak sağlayabilirsiniz.

Kaynakları var olan bir kaynaktan veya yürütülebilir dosyadan geçerli kaynak dosyanıza kolayca kopyalayabilirsiniz. Kaynakları kopyalamak için, her iki dosyayı aynı anda açar ve öğeleri bir dosyadan diğerine sürükleyin veya iki Dosya arasında kopyalayıp yapıştırın. Bu yöntem, kaynak betiği (. RC) dosyaları ve kaynak şablonu (. rct) dosyaları ve yürütülebilir (. exe) dosyaları için geçerlidir.

> [!NOTE]
> Visual C++, kendi uygulamanızda kullanabileceğiniz örnek kaynak dosyalarını içerir. Daha fazla bilgi için bkz. [CLIPART: Common Resources](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/general).

Projedeki kaynak dosyaları (**kaynak görünümü**) ve tek başına. RC dosyaları arasında sürükleyip bırakamazsınız, kopyalayamaz, kesebilir veya yapıştıramazsınız. Bunu ürünün önceki sürümlerinde yapabilirsiniz. Yalnızca proje dışında açık olan. RC dosyaları arasında sürükle ve bırak yöntemini kullanın.

### <a name="to-copy-resources"></a>Kaynakları kopyalamak için

1. Her iki kaynak dosyasını tek başına açın. (Bkz. [kaynak komut dosyalarını kullanma](how-to-create-a-resource-script-file.md#use-resource-script-files)). Örneğin, *Source1. RC* ve *source2. RC*' yi açın.

1. İlk. rc dosyasının içinde, aşağıdakilerden birini yapın:

   - Sürükle ve bırak yöntemini kullanma

      1. Kopyalamak istediğiniz kaynağı seçin. Örneğin, *Source1. RC*' de **IDD_DIALOG1**' yi seçin.

      1. **CTRL** tuşunu basılı tutun ve kaynağı ikinci. rc dosyasına sürükleyin. Örneğin, *Source1. RC* öğesinden *source2. RC*'ye **IDD_DIALOG1** sürükleyin.

         > [!TIP]
         > Kaynağı **CTRL** tuşunu basılı tutmaya gerek kalmadan sürüklemek, kaynağı kopyalamak yerine bir konuma taşımakta.

   - Kopyala ve Yapıştır yöntemini kullanma

      1. Kopyalamak istediğiniz kaynağa (örneğin, *Source1. RC*) sağ tıklayın ve **Kopyala**' yı seçin.

      1. Kaynağı yapıştırmak istediğiniz kaynak dosyasına (örneğin, *source2. RC*) sağ tıklayın ve **Yapıştır**' ı seçin.

> [!NOTE]
> Varolan dosyadaki sembol adlarıyla veya değerlerle çakışmayı önlemek için Visual C++, aktarılan kaynağın sembol değerini veya sembol adını ve değerini yeni dosyaya kopyaladığınızda değiştirebilir.

Bir kaynağa kopyalarken, kendi dil özelliğini veya koşul özelliğini ya da her ikisini de değiştirebilirsiniz.

- Bir kaynağın dili, aradığınız kaynağın tanımlanmasına yardımcı olmak için [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcea) tarafından kullanılan dili belirtir. Kaynaklar, metinle ilgili olmayan her dil için, örneğin yalnızca Japonca bir klavyede veya yalnızca Çince yerelleştirilmiş derlemeler için uygun bir bit eşlemde çalışan Hızlandırıcılar için farklılık gösterebilir.

- Bir kaynağın koşulu, kaynağın bu kopyasının kullanılacağı koşulu tanımlayan tanımlı bir simgedir.

Bir kaynağın dili ve koşulu, **çalışma alanı** penceresinde kaynağın adından sonra parantez içinde gösterilir. Burada adlı kaynak, `IDD_AboutBox` `Finnish` dili olarak kullanılıyor ve durumu şu şekildedir `XX33` :

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Var olan bir kaynağı kopyalamak ve dilini veya koşulunu değiştirmek için

*. RC* dosyasında veya [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) penceresinde, kopyalamak istediğiniz kaynağa sağ tıklayın ve **kopya Ekle**' yi seçin. Ardından şunları ayarlayın:

- **Dil** liste kutusu için dili seçin.

- **Koşul** kutusuna koşulu yazın.

### <a name="to-edit-resources"></a>Kaynakları düzenlemek için

Yönetilen kaynak (. resx) dosyaları XML dosyalarıdır. Projenize bir yönetilen kaynak dosyası eklediğinizde **Yeni öğe Ekle** iletişim kutusundan, **yönetilen kaynaklar Düzenleyicisi** varsayılan olarak açılır.

## <a name="import-and-export-resources"></a>Kaynakları İçeri ve Dışarı Aktarma

Visual C++ kullanım için grafik kaynaklarını (bit eşlemler, simgeler, imleçler ve araç çubukları), HTML dosyalarını ve özel kaynakları içeri aktarabilirsiniz. Visual Studio C++ projesinden aynı dosya türlerini, geliştirme ortamının dışında kullanılabilecek dosyaları ayrı dışa aktarabilirsiniz.

> [!NOTE]
> Tek başına dosya türleri olmadığından Hızlandırıcılar, iletişim kutuları ve dize tabloları gibi kaynak türleri içeri aktarılamaz veya verilemez.

### <a name="to-import-a-resource-into-the-resource-script-file"></a>Kaynak betik dosyasına bir kaynağı içeri aktarmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) , kaynak eklemek istediğiniz kaynak betiği (. RC) dosyasının düğümüne sağ tıklayın ve **içeri aktar**' ı seçin.

1. Bit eşlem (. bmp), simge (. ico), imleç (. cur), HTML dosyası (. htm) veya içe aktarılacak başka bir dosyanın dosya adını bulun ve seçin.

1. Kaynağı kaynak betik dosyasına eklemek için **Tamam ' ı** seçin.

> [!NOTE]
> İçeri aktarma işlemi, seçtiğiniz kaynak türü ne olduğuna bakılmaksızın aynı şekilde işler. İçeri aktarılan kaynak, kaynak türünün doğru düğümüne otomatik olarak eklenir.

### <a name="to-export-a-resource-for-use-outside-of-visual-c"></a>Visual C++ dışında kullanmak üzere bir kaynağı dışarı aktarmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), dışarı aktarmak istediğiniz kaynağa sağ tıklayın ve **dışarı aktar**' ı seçin. Geçerli dosya adını kabul edebilir veya yeni bir tane yazabilirsiniz.

1. Dosyayı kaydetmek istediğiniz klasöre gidin ve **dışarı aktar**' ı seçin.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource-script-file.md)<br/>
[Nasıl yapılır: derleme zamanında kaynakları dahil etme](../windows/how-to-include-resources-at-compile-time.md)
