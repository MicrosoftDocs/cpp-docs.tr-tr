---
title: 'Nasıl yapılır: Kaynaklarını kopyalama (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
- vc.resvw.resource.changing
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
- Language property [C++]
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 772c9b905d4cb0c4e2ccab9ec51aa02860b2db32
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849667"
---
# <a name="how-to-copy-resources-c"></a>Nasıl yapılır: Kaynaklarını kopyalama (C++)

Kaynakları bir dosyadan başka değişiklik yapmadan kopyalayabilir veya kopyalama sırasında dilini veya koşulunu kaynağın değiştirebilirsiniz.

Kolayca kaynakları bir var olan bir kaynak veya yürütülebilir dosyanın geçerli kaynak dosyaya kopyalayabilirsiniz. Kaynak kopyalamak için kaynakları içeren aynı anda hem dosyaları açmak ve öğeleri bir dosyadan sürükleyin veya kopyalayıp iki dosya arasında. Bu yöntem, kaynak betiği (.rc) dosyalarını ve kaynak şablonu (.rct) dosyaları ve yürütülebilir (.exe) dosyaları olarak çalışır.

> [!NOTE]
> Visual C++, kendi uygulamanızda kullanabileceğiniz örnek kaynak dosyalarını içerir. Daha fazla bilgi için [küçük: Ortak kaynakları](https://github.com/Microsoft/VCSamples).

Açık olan .rc dosyası arasında sürükle ve bırak yöntemi kullanabileceğiniz [proje dışında](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

## <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>Sürükle ve bırak yöntemiyle dosyaları arasında kaynakları kopyalama

1. Tek başına hem de kaynak dosyalarını açın (daha fazla bilgi için [bir .rc dosyasının dışında sonuna bir proje içinde kaynaklar görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, Source1.rc ve Source2.rc açın.

1. İlk .rc dosyası kopyalamak istediğiniz kaynağı seçin. Örneğin, `Source1.rc`seçin **IDD_DIALOG1**.

1. Basılı **Ctrl** anahtar ve ikinci .rc dosyası için kaynak sürükleyin. Örneğin, sürükleyin **IDD_DIALOG1** gelen `Source1.rc` için `Source2.rc`.

   > [!NOTE]
   > Basılı tutulmadan kaynak sürükleyerek **Ctrl** kopyalamak yerine kaynak anahtarı taşır.

## <a name="to-copy-resources-using-copy-and-paste"></a>Kopyalama kullanarak kaynakları kopyalamak ve yapıştırmak için

1. Tek başına hem de kaynak dosyalarını açın (daha fazla bilgi için [bir .rc dosyasının dışında sonuna bir proje içinde kaynaklar görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, Source1.rc ve Source2.rc.

1. İçinden istediğiniz bir kaynak kopyalamak kaynak dosyasında (örneğin, `Source1.rc`), bir kaynağa sağ tıklayın ve seçin **kopyalama** kısayol menüsünden.

1. İçine istediğiniz kaynak yapıştırın kaynak dosyaya sağ tıklayın (örneğin, `Source2.rc`). Seçin **Yapıştır** kısayol menüsünden.

   > [!NOTE]
   > Sürükleyin ve bırakın, kesme, kopyalayamaz veya projedeki kaynak dosyaları arasında yapıştırın (**kaynak görünümü**) ve tek başına .rc dosyaları (Bu belge pencerelerinin açık). Bu ürünün önceki sürümlerinde yapabilirsiniz.

   > [!NOTE]
   > Yeni dosyayı kopyaladığınızda, sembol adlarını veya var olan dosyayı değerleri ile çakışmaları önlemek için Visual C++ aktarılan kaynak sembol değeri veya sembol adını ve değerini değişebilir.

## <a name="to-change-the-language-or-condition-of-a-resource-while-copying-c"></a>(C++) kopyalanırken dilini veya koşulunu bir kaynağı değiştirmek için

Bir kaynak olarak kopyalarken, kendi dil özelliği veya koşul özelliğini veya her ikisi de değiştirebilirsiniz.

- Kaynağın dilini yalnızca, kaynak için dil tanımlar. Dili tarafından kullanılan [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) , aradığınız kaynak belirlemenize yardımcı olması için. (Ancak metne ilişkili olmayan farklar her dil için kaynaklara sahip olabilir, örneğin, Japonca klavyede yalnızca işe yarayabilir Hızlandırıcıları ya da yalnızca yerelleştirilmiş Çince uygun olacağı bir bit eşlem oluşturur.)

- Bir kaynağı tanımlayan bir koşul altında kullanılacak bu belirli kaynak kopyası olan bir tanımlanmış sembol durumdur.

Dil ve kaynak durumunu çalışma alanı penceresini kaynak adından sonra parantez içinde gösterilmektedir. Bu örnekte, IDD_AboutBox adlı kaynağın Dili Fince kullanıyor ve XX33 kendi durumdur.

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Mevcut bir kaynağı kopyalayın ve kendi dilini veya koşulunu değiştirme

1. .Rc dosyasının veya [kaynak görünümü](../windows/resource-view-window.md) penceresi, kopyalamak istediğiniz kaynağa sağ tıklayın.

1. Seçin **Ekle kopyalama** kısayol menüsünden.

1. İçinde **kaynak kopyasını Ekle** iletişim kutusunda:

   - İçin **dil** liste kutusunda, bir dil seçin.

   - İçinde **koşul** koşul yazın.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Nasıl yapılır: Proje Dışındaki Kaynak Betik Dosyasını Açma (Tek Başına)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
