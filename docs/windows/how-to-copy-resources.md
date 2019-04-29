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
ms.openlocfilehash: 6b9499fbd806c04774d12750c70816d0312a4e3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345272"
---
# <a name="how-to-manage-resources-c"></a>Nasıl yapılır: Kaynaklar (C++) yönetme

## <a name="copy-and-edit-resources"></a>Kopyalama ve düzenleme kaynakları

Kaynakları bir dosyadan başka değiştirmenizi veya kopyalama sırasında dilini veya koşulunu bir kaynağı değiştirme olmadan kopyalayabilirsiniz.

Kolayca kaynakları bir var olan bir kaynak veya yürütülebilir dosyanın geçerli kaynak dosyaya kopyalayabilirsiniz. Kaynak kopyalamak için kaynakları içeren aynı anda hem dosyaları açmak ve öğeleri bir dosyadan sürükleyin veya kopyalayıp iki dosya arasında. Bu yöntem, kaynak betiği (.rc) dosyalarını ve kaynak şablonu (.rct) dosyaları ve yürütülebilir (.exe) dosyaları olarak çalışır.

> [!NOTE]
> Visual C++, kendi uygulamanızda kullanabileceğiniz örnek kaynak dosyalarını içerir. Daha fazla bilgi için [küçük: Ortak kaynakları](https://github.com/Microsoft/VCSamples).

Sürükleyin ve bırakın, kesme, kopyalayamaz veya projedeki kaynak dosyaları arasında yapıştırın (**kaynak görünümü**) ve belge pencerelerinin tek başına bir .rc dosyası açın. Bu ürünün önceki sürümlerinde yapabilirsiniz. Yalnızca projenin dışında açık olan .rc dosyası arasında sürükle ve bırak yöntemini kullanın.

### <a name="to-copy-resources"></a>Kaynak kopyalamak için

1. Tek başına hem de kaynak dosyalarını açın. (Bkz [kaynak betik dosyalarına kullanın](how-to-create-a-resource-script-file.md#use-resource-script-files)). Örneğin, açmak *Source1.rc* ve *Source2.rc*.

1. İçinde ilk .rc dosyası ya da:

   - Sürükle ve bırak yöntemini kullanın

      1. Kopyalamak istediğiniz kaynağı seçin. Örneğin, *Source1.rc*seçin **IDD_DIALOG1**.

      1. Basılı **Ctrl** anahtar ve ikinci .rc dosyası için kaynak sürükleyin. Örneğin, sürükleyin **IDD_DIALOG1** gelen *Source1.rc* için *Source2.rc*.

         > [!TIP]
         > Basılı tutulmadan kaynak sürükleyerek **Ctrl** kopyalamak yerine kaynak anahtarı taşır.

   - Kopyala ve Yapıştır yöntemi

      1. Kaynağa sağ sizinle kopyalamak için (örneğin, *Source1.rc*) seçip **kopyalama**.

      1. İçine istediğiniz kaynak yapıştırın kaynak dosyaya sağ tıklayın (örneğin, *Source2.rc*) seçip **yapıştırın**.

> [!NOTE]
> Yeni dosyayı kopyaladığınızda, sembol adlarını veya var olan dosyayı değerleri ile çakışmaları önlemek için Visual C++ aktarılan kaynak sembol değeri veya sembol adını ve değerini değişebilir.

Bir kaynak olarak kopyalarken, kendi dil özelliği veya koşul özelliğini veya her ikisi de değiştirebilirsiniz.

- Tarafından kullanılan dil olan bir kaynağın dilini belirtir [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) , aradığınız kaynak belirlemenize yardımcı olması için. Metne ilişkili olmayan farklar her dil için kaynaklara sahip olabilir, örneğin, Japonca klavyede yalnızca işe yarayabilir Hızlandırıcıları ya da yalnızca yerelleştirilmiş Çince uygun olacağı bir bit eşlem oluşturur.

- Bir kaynağı tanımlayan bir koşul altında kullanılacak bu belirli kaynak kopyası olan bir tanımlanmış sembol durumdur.

Dil ve kaynak durumu, parantez içine kaynak adından sonra gösterilir **çalışma** penceresi. Burada kaynak adlı `IDD_AboutBox` kullanıyor `Finnish` kendi dil ve bunun koşul `XX33`:

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Mevcut bir kaynağı kopyalayın ve kendi dilini veya koşulunu değiştirme

İçinde *.rc* dosya veya [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) penceresinde kopyalayın ve istediğiniz kaynağa sağ **Ekle kopyalama**. Ardından aşağıdakileri ayarlayın:

- İçin **dil** liste kutusunda, bir dil seçin.

- İçinde **koşul** koşul yazın.

### <a name="to-edit-resources"></a>Kaynakları düzenlemek için

Yönetilen kaynak (.resx) dosyaları XML dosyalarıdır. Yönetilen kaynak dosyasını projenizden eklediğinizde **Yeni Öğe Ekle** iletişim kutusu, **yönetilen kaynaklar düzenleyicisini** varsayılan olarak açılır.

## <a name="import-and-export-resources"></a>İçeri ve dışarı aktarma kaynakları

Grafik kaynakları (bit eşlemler, simgeler, işaretçiler ve araç çubukları), HTML dosyaları ve Visual C++'ta kullanmak için özel kaynaklar içeri aktarabilirsiniz. Geliştirme ortamının dışında kullanılan dosyaları ayırmak için bir Visual C++ projesi aynı dosya türlerini dışarı aktarabilirsiniz.

> [!NOTE]
> Dize tabloları hızlandırıcıları ve iletişim kutuları gibi kaynak türleri içeri aktarılabilir veya değil tek başına dosya türleri olduğundan dışarı.

### <a name="to-import-a-resource-into-the-resource-script-file"></a>Kaynak betik dosyasına bir kaynak içeri aktarmak için

1. İçinde [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) düğümü istediğiniz bir kaynak ekleyin ve seçmek kaynak betiği (.rc) dosyasının **alma**.

1. Bulun ve bit eşlem (.bmp), simge (.ico), imleç (.cur), html dosyası (.htm) veya başka bir dosyayı içeri aktarmak için dosya adını seçin.

1. Seçin **Tamam** kaynak kaynak betik dosyasına eklenecek.

> [!NOTE]
> İçeri aktarma işlemi hangi kaynak türünü olursa olsun seçtiğiniz aynı şekilde çalışır. İçeri aktarılan kaynak, kaynak türü doğru düğüme otomatik olarak eklenir.

### <a name="to-export-a-resource-for-use-outside-of-visual-c"></a>Visual C++ dışında kullanmak için bir kaynak dışarı aktarmak için

1. İçinde [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), seçin ve dışarı aktarmak istediğiniz kaynağa sağ **dışarı**. Geçerli dosya adı kabul edin veya yeni bir tane girin.

1. Dosyayı kaydedin ve seçmek için istediğiniz klasöre gidin **dışarı**.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[Nasıl yapılır: Kaynak oluştur](../windows/how-to-create-a-resource-script-file.md)<br/>
[Nasıl yapılır: Derleme Sırasında Kaynak Ekleme](../windows/how-to-include-resources-at-compile-time.md)<br/>