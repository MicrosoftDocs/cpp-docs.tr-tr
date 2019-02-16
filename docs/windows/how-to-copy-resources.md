---
title: 'Nasıl yapılır: Kaynaklar (C++) yönetme'
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
ms.openlocfilehash: 1f176b3fa19374b402039ecca60e690ade5c0cef
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320633"
---
# <a name="how-to-manage-resources-c"></a>Nasıl yapılır: Kaynaklar (C++) yönetme

## <a name="copy-resources"></a>Kaynakları Kopyala

Kaynakları bir dosyadan başka değişiklik yapmadan kopyalayabilir veya kopyalama sırasında dilini veya koşulunu kaynağın değiştirebilirsiniz.

Kolayca kaynakları bir var olan bir kaynak veya yürütülebilir dosyanın geçerli kaynak dosyaya kopyalayabilirsiniz. Kaynak kopyalamak için kaynakları içeren aynı anda hem dosyaları açmak ve öğeleri bir dosyadan sürükleyin veya kopyalayıp iki dosya arasında. Bu yöntem, kaynak betiği (.rc) dosyalarını ve kaynak şablonu (.rct) dosyaları ve yürütülebilir (.exe) dosyaları olarak çalışır.

> [!NOTE]
> Visual C++, kendi uygulamanızda kullanabileceğiniz örnek kaynak dosyalarını içerir. Daha fazla bilgi için [küçük: Ortak kaynakları](https://github.com/Microsoft/VCSamples).

Açık olan .rc dosyası arasında sürükle ve bırak yöntemi kullanabileceğiniz [proje dışında](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>Sürükle ve bırak yöntemiyle dosyaları arasında kaynakları kopyalama

1. Tek başına hem de kaynak dosyaları açabilir (daha fazla bilgi için [proje dışındaki bir .rc dosyasındaki kaynakları görüntülemek](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, açmak *Source1.rc* ve *Source2.rc*.

1. İlk .rc dosyası kopyalamak istediğiniz kaynağı seçin. Örneğin, *Source1.rc*seçin **IDD_DIALOG1**.

1. Basılı **Ctrl** anahtar ve ikinci .rc dosyası için kaynak sürükleyin. Örneğin, sürükleyin **IDD_DIALOG1** gelen *Source1.rc* için *Source2.rc*.

   > [!NOTE]
   > Basılı tutulmadan kaynak sürükleyerek **Ctrl** kopyalamak yerine kaynak anahtarı taşır.

### <a name="to-copy-resources-using-copy-and-paste"></a>Kopyalama kullanarak kaynakları kopyalamak ve yapıştırmak için

1. Tek başına hem de kaynak dosyaları açabilir (daha fazla bilgi için [proje dışındaki bir .rc dosyasındaki kaynakları görüntülemek](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, *Source1.rc* ve *Source2.rc*.

1. İçinden istediğiniz bir kaynak kopyalamak kaynak dosyasında (örneğin, *Source1.rc*), bir kaynağa sağ tıklayın ve seçin **kopyalama** kısayol menüsünden.

1. İçine istediğiniz kaynak yapıştırın kaynak dosyaya sağ tıklayın (örneğin, *Source2.rc*). Seçin **Yapıştır** kısayol menüsünden.

   > [!NOTE]
   > Sürükleyin ve bırakın, kesme, kopyalayamaz veya projedeki kaynak dosyaları arasında yapıştırın (**kaynak görünümü**) ve tek başına .rc dosyaları (Bu belge pencerelerinin açık). Bu ürünün önceki sürümlerinde yapabilirsiniz.

   > [!NOTE]
   > Yeni dosyayı kopyaladığınızda, sembol adlarını veya var olan dosyayı değerleri ile çakışmaları önlemek için Visual C++ aktarılan kaynak sembol değeri veya sembol adını ve değerini değişebilir.

### <a name="change-the-language-or-condition-of-a-resource-while-copying"></a>Kopyalarken dilini veya koşulunu bir kaynağı değiştirme

Bir kaynak olarak kopyalarken, kendi dil özelliği veya koşul özelliğini veya her ikisi de değiştirebilirsiniz.

- Kaynağın dilini yalnızca, kaynak için dil tanımlar. Dili tarafından kullanılan [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) , aradığınız kaynak belirlemenize yardımcı olması için. (Ancak metne ilişkili olmayan farklar her dil için kaynaklara sahip olabilir, örneğin, Japonca klavyede yalnızca işe yarayabilir Hızlandırıcıları ya da yalnızca yerelleştirilmiş Çince uygun olacağı bir bit eşlem oluşturur.)

- Bir kaynağı tanımlayan bir koşul altında kullanılacak bu belirli kaynak kopyası olan bir tanımlanmış sembol durumdur.

Dil ve kaynak durumu, parantez içine kaynak adından sonra gösterilir **çalışma** penceresi. Bu örnekte, kaynak adlı `IDD_AboutBox` kullanıyor `Finnish` kendi dil ve bunun koşul `XX33`.

```cpp
IDD_AboutBox (Finnish - XX33)
```

#### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Mevcut bir kaynağı kopyalayın ve kendi dilini veya koşulunu değiştirme

1. .Rc dosyasının veya [kaynak görünümü](../windows/resource-view-window.md) penceresi, kopyalamak istediğiniz kaynağa sağ tıklayın.

1. Seçin **Ekle kopyalama** kısayol menüsünü ve aşağıdaki ayarla:

   - İçin **dil** liste kutusunda, bir dil seçin.

   - İçinde **koşul** koşul yazın.

## <a name="edit-resources"></a>Kaynakları düzenleme

Yönetilen kaynak dosyalarını (.resx) XML dosyalarıdır. Yönetilen kaynak dosyasını projenizden eklediğinizde **Yeni Öğe Ekle** iletişim kutusu, **yönetilen kaynaklar düzenleyicisini** varsayılan olarak açılır.

## <a name="import-and-export-resources"></a>İçeri ve dışarı aktarma kaynakları

Grafik kaynakları (bit eşlemler, simgeler, işaretçiler ve araç çubukları), HTML dosyaları ve Visual C++'ta kullanmak için özel kaynaklar içeri aktarabilirsiniz. Geliştirme ortamının dışında kullanılan dosyaları ayırmak için bir Visual C++ projesi aynı dosya türlerini dışarı aktarabilirsiniz.

> [!NOTE]
> Dize tabloları hızlandırıcıları ve iletişim kutuları gibi kaynak türleri içeri aktarılabilir veya tek başına dosya türleri değil olduklarından dışarı.

### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>Tek bir kaynağın geçerli kaynak dosyanızı içeri aktarmak için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), düğümü için kaynak betiği (* .rc) bir kaynak eklemek istediğiniz dosya.

1. Seçin **alma** kısayol menüsünde.

1. Bulun ve bit eşlem (.bmp), simge (.ico), imleç (.cur), Html dosyası (.htm) veya içeri aktarmak istediğiniz başka bir dosyayı dosya adını seçin.

1. Seçin **Tamam** 'teki Seçili dosyanın kaynak eklemek için **kaynak** görünümü.

   > [!NOTE]
   > Belirli kaynağı ne olursa olsun aynı şekilde türünü içeri aktarma işlemi works seçtiniz. İçeri aktarılan kaynak otomatik olarak bu kaynak türü için doğru düğümüne eklenir.

### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>Bir bit eşlem, simgesi veya imleci (Visual C++ dışında kullanın için) ayrı bir dosya olarak dışarı aktarmak için

1. İçinde **kaynak** görüntülemek için dışa aktarmak istediğiniz kaynağa sağ tıklayın.

1. Seçin **dışarı** kısayol menüsünde ve geçerli dosya adı kabul edin veya yeni bir ad yazın.

1. Dosyayı kaydedin ve istediğiniz klasöre gidin **dışarı**.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynakları oluşturma](../windows/how-to-create-a-resource-script-file.md)<br/>
[Derleme sırasında kaynak ekleme](../windows/how-to-include-resources-at-compile-time.md)<br/>